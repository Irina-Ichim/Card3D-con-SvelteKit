<script>
    import img from '../lib/images/Irina.png'
    export let isMouseEntered = false;
    let mouseX = 0;
    let mouseY = 0;
    let cardRotationY = 0;
    let cardRotationX = 0;
    const sensitivity = 2;

    function handleMouseMove(event) {
        const card = event.currentTarget.getBoundingClientRect();
        const cardCenterX = card.left + card.width / 2;
        const cardCenterY = card.top + card.height / 2;
        mouseX = event.clientX;
        mouseY = event.clientY;

        // Calculamos la rotación en función de la posición del cursor,
        // multiplicada por el factor de sensibilidad y suavizamos los movimientos
        cardRotationY += ((mouseX - cardCenterX) / cardCenterX) * 1 * sensitivity;
        cardRotationX += ((mouseY - cardCenterY) / cardCenterY) * 1 * sensitivity;
        
        // Limitamos la rotación para que no sea excesiva
        cardRotationY = Math.min(Math.max(cardRotationY, -15), 15);
        cardRotationX = Math.min(Math.max(cardRotationX, -15), 15);
    }
</script>


<style>
    .card-container {
        perspective: 1000px;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 500px;
    }

    .card {
        width: 320px;
        height: 480px;
        background-color: #fff;
        border-radius: 20px;
        box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.1);
        transition: transform 0.3s;
        transform-style: preserve-3d;
    }

    .card:hover {
        transform: rotateY(10deg) rotateX(10deg) scale(1.05);
    }

    .card-content {
        padding: 20px;
        text-align: center;
    }

    .card-title {
        font-size: 24px;
        font-weight: bold;
        margin-bottom: 10px;
        color: rgba(221, 74, 255, 0.8);
    }

    .card-description {
        font-size: 16px;
        color: #333;
        margin-bottom: 20px;
    }

    .card-image {
        width: 100%;
        height: 200px;
        border-radius: 20px 20px 0 0;
        object-fit: cover;
    }

    .card-actions {
        display: flex;
        justify-content: space-around;
        align-items: center;
        padding: 20px;
    }

    .action-button {
        padding: 10px 20px;
        border-radius: 10px;
        font-size: 16px;
        font-weight: bold;
        background-color:  rgba(18, 113, 255, 0.8) ;
        cursor: pointer;
        transition: background-color 0.3s;
    }
    a{
        text-decoration: none;
        color: white;
    }

    .action-button:hover {
        background-color: rgba(221, 74, 255, 0.8);
    }
</style>

<div class="card-container" role="presentation" on:mousemove={handleMouseMove} on:mouseleave={() => isMouseEntered = false}>
    <div class="card" style="transform: rotateY({cardRotationY}deg) rotateX({cardRotationX}deg) translateZ(-20px) scale(1.1);">
        <img src={img} class="card-image" alt="thumbnail">
        <div class="card-content">
            <div class="card-title">Full Stack Developer</div>
            <div class="card-description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus, qui, aliquid iure delectus accusantium corrupti deserunt temporibus explicabo blanditiis praesentium totam officia! Iure velit rerum quis voluptatem eaque laboriosam ratione.</div>
            <div class="card-actions">
                <div class="action-button"><a href="https://www.linkedin.com/in/irina-ichim-desarolladora/" target="_blank">LinkedIn</a></div>
                <div class="action-button"><a href="https://github.com/Irina-Ichim" target="_blank">GitHub</a></div>

            </div>
        </div>
    </div>
</div>





