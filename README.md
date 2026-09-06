# BUGATTI-TYPE57-ALANTIC-3D-MODLE

import bpy

# Image paths
images = [
    "Renders/C001.png",  # Clay
    "Renders/T001.png",  # Topology
    "Renders/Z001.png",  # Zebra
    "Renders/R001.png",  # Render
]

# Output
output_path = "Renders/Destrier_Showcase.mp4"

# Animation settings
FPS = 30
PANEL_WIDTH = 480
PANEL_HEIGHT = 270
DURATION_PER_IMAGE = 3
SLIDE_DURATION = 1

# Create a new scene
scene = bpy.context.scene
scene.render.engine = 'BLENDER_EEVEE_NEXT'
scene.render.resolution_x = PANEL_WIDTH * 4
scene.render.resolution_y = PANEL_HEIGHT
scene.render.resolution_percentage = 100
scene.render.fps = FPS

# Clear scene
bpy.ops.object.select_all(action='SELECT')
bpy.ops.object.delete(use_global=False)

# Create four panels
for i, image_path in enumerate(images):

    # Load image
    try:
        img = bpy.data.images.load(bpy.path.abspath("//" + image_path))
    except:
        print("Could not load:", image_path)
        continue

    # Create plane
    bpy.ops.mesh.primitive_plane_add(size=2)
    plane = bpy.context.object
    plane.name = f"Panel_{i+1}"

    # Scale plane to panel aspect ratio
    plane.scale = (PANEL_WIDTH / PANEL_HEIGHT, 1, 1)

    # Material
    mat = bpy.data.materials.new(f"Material_{i+1}")
    mat.use_nodes = True

    nodes = mat.node_tree.nodes
    links = mat.node_tree.links

    nodes.clear()

    tex = nodes.new("ShaderNodeTexImage")
    tex.image = img

    emission = nodes.new("ShaderNodeEmission")
    output = nodes.new("ShaderNodeOutputMaterial")

    links.new(tex.outputs["Color"], emission.inputs["Color"])
    links.new(emission.outputs["Emission"], output.inputs["Surface"])

    plane.data.materials.append(mat)

    # Position panel
    plane.location.x = (i - 1.5) * 2.1

# Camera
bpy.ops.object.camera_add(location=(0, 0, 10))
camera = bpy.context.object
scene.camera = camera

camera.data.type = 'ORTHO'
camera.data.ortho_scale = 8.4

# Camera looks down
camera.rotation_euler = (0, 0, 0)

# Output settings
scene.render.image_settings.file_format = 'FFMPEG'
scene.render.ffmpeg.format = 'MPEG4'
scene.render.ffmpeg.codec = 'H264'
scene.render.filepath = bpy.path.abspath("//" + output_path)

# Timeline
scene.frame_start = 1
scene.frame_end = DURATION_PER_IMAGE * FPS * 4

print("Destrier showcase setup complete.")
