# msfs_probe

[note:This is currently the FSX code]

Creates AI objects and moves them around (in this case to positions relative to the user aircraft)
to 'probe' the terrain.

Using AI probes is fairly general. The use-case here is to find the ground elevations around
the user aircraft and calculate an appropriate 'ridge lift' value given the prevailing wind speed
and direction.

[note: The code currently combines some other stuff, particularly recording the lat/lng/alt of the
user aircraft to an IGC-format file - this should be broken out into clear separate programs at some
point ... ]
