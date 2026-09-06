# BUGATTI-TYPE57-ALANTIC-3D-MODLE

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Bugatti Destrier Showcase</title>

<style>

    * {
        box-sizing: border-box;
    }

    html, body {
        margin: 0;
        width: 100%;
        height: 100%;
        background: #000;
        overflow: hidden;
    }

    body {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    /* =====================================================
       MAIN 16:9 CANVAS
       ===================================================== */

    .showcase {
        width: min(100vw, 177.7778vh);
        height: min(100vh, 56.25vw);

        display: grid;
        grid-template-columns: repeat(4, 1fr);

        background: #000;

        overflow: hidden;
    }


    /* =====================================================
       FIXED PANELS
       ===================================================== */

    .panel {
        position: relative;

        width: 100%;
        height: 100%;

        overflow: hidden;

        background: #000;

        border-right: 2px solid #000;
    }

    .panel:last-child {
        border-right: none;
    }


    /* =====================================================
       IMAGE
       ===================================================== */

    .panel img {
        position: absolute;

        top: 0;
        left: 0;

        height: 100%;
        width: auto;

        max-width: none;

        object-fit: cover;

        transform: translateX(0);

        animation-name: slide;
        animation-duration: 8s;
        animation-timing-function: ease-in-out;
        animation-iteration-count: infinite;
        animation-direction: alternate;
    }


    /* =====================================================
       SLIDING ANIMATION
       ===================================================== */

    @keyframes slide {

        0% {
            transform: translateX(0%);
        }

        25% {
            transform: translateX(-25%);
        }

        50% {
            transform: translateX(-50%);
        }

        75% {
            transform: translateX(-75%);
        }

        100% {
            transform: translateX(-75%);
        }

    }


    /* =====================================================
       OPTIONAL PANEL LABELS
       ===================================================== */

    .label {
        position: absolute;

        left: 20px;
        bottom: 20px;

        z-index: 10;

        color: white;

        font-family:
            Arial,
            Helvetica,
            sans-serif;

        font-size: 14px;
        font-weight: 600;

        letter-spacing: 2px;

        text-transform: uppercase;

        text-shadow:
            0 2px 10px rgba(0,0,0,0.8);

        pointer-events: none;
    }

</style>
</head>


<body>


<!-- =======================================================
     4 FIXED WINDOWS
     ======================================================= -->

<div class="showcase">


    <!-- ================= CLAY ================= -->

    <div class="panel">

        <img
            src="Renders/C001.png"
            alt="Destrier Clay"
        >

        <div class="label">
            CLAY
        </div>

    </div>


    <!-- ================= TOPOLOGY ================= -->

    <div class="panel">

        <img
            src="Renders/T001.png"
            alt="Destrier Topology"
        >

        <div class="label">
            TOPOLOGY
        </div>

    </div>


    <!-- ================= ZEBRA ================= -->

    <div class="panel">

        <img
            src="Renders/Z001.png"
            alt="Destrier Zebra Analysis"
        >

        <div class="label">
            ZEBRA
        </div>

    </div>


    <!-- ================= FINAL ================= -->

    <div class="panel">

        <img
            src="Renders/R001.png"
            alt="Destrier Final Render"
        >

        <div class="label">
            FINAL
        </div>

    </div>


</div>


</body>
</html>
