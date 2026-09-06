# BUGATTI-TYPE57-ALANTIC-3D-MODLE

<svg
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    viewBox="0 0 1920 1080"
    width="100%"
>

    <defs>

        <!-- ============================= -->
        <!-- PANEL 1 CLIP -->
        <!-- ============================= -->

        <clipPath id="clip1">
            <rect x="0" y="0" width="480" height="1080"/>
        </clipPath>

        <!-- ============================= -->
        <!-- PANEL 2 CLIP -->
        <!-- ============================= -->

        <clipPath id="clip2">
            <rect x="480" y="0" width="480" height="1080"/>
        </clipPath>

        <!-- ============================= -->
        <!-- PANEL 3 CLIP -->
        <!-- ============================= -->

        <clipPath id="clip3">
            <rect x="960" y="0" width="480" height="1080"/>
        </clipPath>

        <!-- ============================= -->
        <!-- PANEL 4 CLIP -->
        <!-- ============================= -->

        <clipPath id="clip4">
            <rect x="1440" y="0" width="480" height="1080"/>
        </clipPath>

    </defs>


    <!-- ========================================= -->
    <!-- BACKGROUND -->
    <!-- ========================================= -->

    <rect
        width="1920"
        height="1080"
        fill="#050505"
    />


    <!-- ========================================= -->
    <!-- PANEL 1 — CLAY -->
    <!-- ========================================= -->

    <g clip-path="url(#clip1)">

        <image
            xlink:href="Renders/C001.png"
            x="0"
            y="0"
            width="1920"
            height="1080"
            preserveAspectRatio="none"
        >

            <animate
                attributeName="x"
                values="0;-480;-960;-1440;-960;-480;0"
                dur="12s"
                repeatCount="indefinite"
            />

        </image>

    </g>


    <!-- ========================================= -->
    <!-- PANEL 2 — TOPOLOGY -->
    <!-- ========================================= -->

    <g clip-path="url(#clip2)">

        <image
            xlink:href="Renders/T001.png"
            x="480"
            y="0"
            width="1920"
            height="1080"
            preserveAspectRatio="none"
        >

            <animate
                attributeName="x"
                values="480;0;-480;-960;-480;0;480"
                dur="12s"
                repeatCount="indefinite"
            />

        </image>

    </g>


    <!-- ========================================= -->
    <!-- PANEL 3 — ZEBRA -->
    <!-- ========================================= -->

    <g clip-path="url(#clip3)">

        <image
            xlink:href="Renders/Z001.png"
            x="960"
            y="0"
            width="1920"
            height="1080"
            preserveAspectRatio="none"
        >

            <animate
                attributeName="x"
                values="960;480;0;-480;0;480;960"
                dur="12s"
                repeatCount="indefinite"
            />

        </image>

    </g>


    <!-- ========================================= -->
    <!-- PANEL 4 — FINAL -->
    <!-- ========================================= -->

    <g clip-path="url(#clip4)">

        <image
            xlink:href="Renders/R001.png"
            x="1440"
            y="0"
            width="1920"
            height="1080"
            preserveAspectRatio="none"
        >

            <animate
                attributeName="x"
                values="1440;960;480;0;480;960;1440"
                dur="12s"
                repeatCount="indefinite"
            />

        </image>

    </g>


    <!-- ========================================= -->
    <!-- PANEL DIVIDERS -->
    <!-- ========================================= -->

    <rect
        x="478"
        y="0"
        width="4"
        height="1080"
        fill="#111111"
    />

    <rect
        x="958"
        y="0"
        width="4"
        height="1080"
        fill="#111111"
    />

    <rect
        x="1438"
        y="0"
        width="4"
        height="1080"
        fill="#111111"
    />

</svg>
