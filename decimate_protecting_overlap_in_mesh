import bpy

#create object

bpy.ops.mesh.primitive_cube_add(enter_editmode=False, align='WORLD', location=(0, 0, 0), scale=(1, 1, 1))


#get object

obj1 = bpy.data.objects["Cube"]


#subdivide + shade smooth object

bpy.ops.object.mode_set(mode="EDIT")
bpy.ops.mesh.subdivide(number_cuts=10, smoothness=1.0)
bpy.ops.object.mode_set(mode="OBJECT")

for f in obj1.data.polygons:
    f.use_smooth = True

#duplicate object

bpy.ops.object.duplicate(linked=False)
obj2 = bpy.data.objects["Cube.001"]

#get cutter object

obj3 = bpy.data.objects["Selector"]

#apply intersect boolean to get overlapping area

bool = obj2.modifiers.new(type="BOOLEAN", name="bool")
bool.object = obj3
bool.operation = "INTERSECT"

bpy.ops.object.modifier_apply(modifier="bool")
obj3.hide_set(True)

#create vertex group

new_vertex_group = obj1.vertex_groups.new(name="dont_decimate")
vertex_group_data = []

#check for each vertex of the original if the vertex exists in the modified copy
for v1 in obj1.data.vertices:
     for v2 in obj2.data.vertices:
        if v1.co == v2.co:
            vertex_group_data.append(v1.index)
            
print(vertex_group_data)

#add selection to the vertex group

new_vertex_group.add(vertex_group_data, 1.0, 'ADD')

#add decimate modifier

decimate = obj1.modifiers.new(type="DECIMATE",name="decimate")
decimate.ratio = 0.2

#preserve vertex group

decimate.vertex_group = "dont_decimate"
decimate.invert_vertex_group = True

#apply modifier (optional)
#bpy.context.view_layer.objects.active = obj1
#bpy.ops.object.modifier_apply(modifier="bool")

obj2.hide_set(True)







