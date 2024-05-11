<script>
    export let isMouseEntered = false;
    let mouseX = 0;
    let mouseY = 0;
    let cardRotationY = 0;
    let cardRotationX = 0;
    const sensitivity = 1;

    function handleMouseMove(event) {
      const card = event.currentTarget.getBoundingClientRect();
      const cardCenterX = card.left + card.width / 2;
      const cardCenterY = card.top + card.height / 2;
      mouseX = event.clientX;
      mouseY = event.clientY;
  
      // Calculamos la rotación en función de la posición del cursor, multiplicada por el factor de sensibilidad
      cardRotationY = ((mouseX - cardCenterX) / cardCenterX) * 15 * sensitivity;
      cardRotationX = ((mouseY - cardCenterY) / cardCenterY) * 15 * sensitivity;
    }
</script>
  
<style>
    .card-container {
        perspective: 1000px;
    }

    .card {
        width: auto;
        max-width: 30rem;
        height: auto;
        padding: 1.5rem;
        background-color: #f7fafc;
        border: 1px solid #cbd5e0;
        border-radius: 0.75rem;
        transition: transform 0.3s;
        margin-left: 90px;
        margin-top: 150px;
    }

    .card:hover {
        transform: rotateY(5deg) rotateX(5deg) scale(1.05);
    }

    .card:hover .card-content {
        transform: translateY(-20px);
    }

    .card:hover .card-actions {
        opacity: 1;
        visibility: visible;
        transform: translateY(0);
    }

    .card-content {
        font-size: 1.25rem;
        font-weight: bold;
        margin-bottom: 1rem;
        transition: transform 0.3s;
    }

    .card-description {
        font-size: 1rem;
        color: #4a5568;
        margin-bottom: 1rem;
    }

    .card-image {
        width: 100%;
        height: auto;
        border-radius: 0.5rem;
    }

    .card-actions {
        display: flex;
        justify-content: space-between;
        align-items: center;
        opacity: 0;
        visibility: hidden;
        transition: opacity 0.3s, visibility 0.3s, transform 0.3s;
        transform: translateY(10px);
    }

    .action-button {
        padding: 0.5rem 1rem;
        border-radius: 0.5rem;
        font-size: 0.875rem;
        font-weight: bold;
        color: #ffffff;
        cursor: pointer;
        transition: background-color 0.3s;
    }

    .action-button:hover {
        background-color: #4a90e2;
    }
</style>

<div class="card-container" role="presentation" on:mousemove={handleMouseMove} on:mouseleave={() => isMouseEntered = false}>
    <div class="card" style="transform: rotateY({cardRotationY}deg) rotateX({cardRotationX}deg);">
        <div class="card-content">Make things float in air</div>
        <div class="card-description">Hover over this card to unleash the power of CSS perspective</div>
        <img src="https://images.unsplash.com/photo-1441974231531-c6227db76b6e?q=80&w=2560&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" class="card-image" alt="thumbnail">
        <div class="card-actions">
            <div class="action-button">Try now →</div>
            <div class="action-button" style="background-color: #000000;">Sign up</div>
        </div>
    </div>
</div>


