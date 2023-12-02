<script>
    import { Slide } from '@components'
    import { animate, signal } from '@motion'
  
    let progress = signal(0)
    
    animate(async () => {
      await progress.to(315)
    })
  </script>
  
  
  #{$progress.toLocaleString('en', { maximumFractionDigits: 0 })}
