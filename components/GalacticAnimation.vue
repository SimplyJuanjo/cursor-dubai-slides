<template>
  <div class="w-full h-full relative flex items-center justify-center overflow-hidden">
    <div ref="p5Container" class="absolute inset-0"></div>
    <div class="relative z-10 text-center">
      <h1 class="text-4xl md:text-6xl font-bold text-white mb-4 animate-pulse drop-shadow-2xl">
        My 3D skills are null,
      </h1>
      <h2 class="text-3xl md:text-5xl font-bold text-cyan-300 animate-bounce drop-shadow-2xl">
        but Cursor is magic ✨
      </h2>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import p5 from 'p5'

const p5Container = ref(null)
let p5Instance = null

onMounted(() => {
  const sketch = (p) => {
    let stars = []
    let galaxy = []
    const numStars = 200
    const numGalaxyParticles = 150
    let time = 0
    
    p.setup = () => {
      const container = p5Container.value
      const width = container.offsetWidth || 800
      const height = container.offsetHeight || 600
      const canvas = p.createCanvas(width, height)
      canvas.parent(container)
      p.colorMode(p.HSB, 360, 100, 100, 100)
      
      // Create background stars
      for (let i = 0; i < numStars; i++) {
        stars.push({
          x: p.random(p.width),
          y: p.random(p.height),
          size: p.random(1, 3),
          brightness: p.random(50, 100),
          twinkle: p.random(0.01, 0.03)
        })
      }
      
      // Create galaxy particles
      for (let i = 0; i < numGalaxyParticles; i++) {
        const angle = p.random(p.TWO_PI)
        const radius = p.random(50, 250)
        galaxy.push({
          angle: angle,
          radius: radius,
          baseRadius: radius,
          speed: p.random(0.005, 0.02),
          size: p.random(2, 8),
          hue: p.random(180, 280), // Blues and purples
          brightness: p.random(60, 100),
          trail: []
        })
      }
    }
    
    p.draw = () => {
      // Dark space background with subtle gradient
      for (let i = 0; i <= p.height; i++) {
        const alpha = p.map(i, 0, p.height, 20, 5)
        p.stroke(240, 80, 10, alpha)
        p.line(0, i, p.width, i)
      }
      
      time += 0.01
      
      // Draw twinkling stars
      for (let star of stars) {
        const twinkle = p.sin(time * star.twinkle) * 30 + star.brightness
        p.fill(0, 0, twinkle, 80)
        p.noStroke()
        p.ellipse(star.x, star.y, star.size)
      }
      
      // Galaxy center
      const centerX = p.width / 2
      const centerY = p.height / 2
      
      // Draw galaxy particles
      for (let particle of galaxy) {
        // Update position
        particle.angle += particle.speed
        
        // Add some spiral effect
        const spiralOffset = p.sin(time + particle.angle * 3) * 20
        particle.radius = particle.baseRadius + spiralOffset
        
        // Calculate position
        const x = centerX + p.cos(particle.angle) * particle.radius
        const y = centerY + p.sin(particle.angle) * particle.radius * 0.6 // Flatten for galaxy effect
        
        // Add to trail
        particle.trail.push({ x, y })
        if (particle.trail.length > 15) {
          particle.trail.shift()
        }
        
        // Draw trail
        p.strokeWeight(1)
        for (let i = 0; i < particle.trail.length - 1; i++) {
          const alpha = p.map(i, 0, particle.trail.length - 1, 10, 60)
          p.stroke(particle.hue, 60, particle.brightness, alpha)
          const current = particle.trail[i]
          const next = particle.trail[i + 1]
          p.line(current.x, current.y, next.x, next.y)
        }
        
        // Draw particle
        const pulseSize = particle.size + p.sin(time * 2 + particle.angle) * 2
        p.fill(particle.hue, 80, particle.brightness, 80)
        p.noStroke()
        p.ellipse(x, y, pulseSize)
        
        // Add glow effect
        p.fill(particle.hue, 40, 100, 20)
        p.ellipse(x, y, pulseSize * 2)
      }
      
      // Central bright core
      const coreSize = 30 + p.sin(time * 2) * 10
      p.fill(200, 80, 100, 60)
      p.ellipse(centerX, centerY, coreSize)
      p.fill(200, 60, 100, 40)
      p.ellipse(centerX, centerY, coreSize * 1.5)
      p.fill(200, 40, 100, 20)
      p.ellipse(centerX, centerY, coreSize * 2)
      
      // Floating particles around the text area
      for (let i = 0; i < 20; i++) {
        const floatX = centerX + p.sin(time + i) * 100
        const floatY = centerY + p.cos(time * 1.5 + i) * 50
        const size = 2 + p.sin(time * 3 + i) * 1
        p.fill(60, 80, 80, 60)
        p.ellipse(floatX, floatY, size)
      }
    }
    
    p.windowResized = () => {
      const container = p5Container.value
      if (container) {
        const width = container.offsetWidth || 800
        const height = container.offsetHeight || 600
        p.resizeCanvas(width, height)
      }
    }
  }
  
  p5Instance = new p5(sketch, p5Container.value)
})

onUnmounted(() => {
  if (p5Instance) {
    p5Instance.remove()
  }
})
</script>

<style scoped>
.drop-shadow-2xl {
  filter: drop-shadow(0 25px 25px rgb(0 0 0 / 0.5));
}
</style>