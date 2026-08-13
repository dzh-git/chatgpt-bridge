Data  Purpose
| Title         |       |       |      |   Title                              |
| ------------- | ----- | ----- | ---- | ------------------------------------ |
| N             | NSYM  |       |      |   Output and symmetry requirements   |
| (blank line)  |       |       |      |                                      |
|               | J1    | J2    | …    | Jn                                   |
| I1            | Z11   | Z12   | …    | Z1n  Table of z-coordinates of each  |
| I2            | Z21   | Z22   | …    | Z2n  principal mesh-point            |
|  .            |   .   |   .   |   .  |   .  (in millimetres)                |
| Im            | Zm1   | Zm2   | …    | Zmn                                  |
| (blank line)  |       |       |      |                                      |
|               | J1    | J2    | …    | Jn                                   |
| I1            | R11   | R12   | …    | R1n  Table of r-coordinates of each  |
| I2            | R21   | R22   | …    | R2n  principal mesh-point            |
|  .            |   .   |   .   |   .  |   .  (in millimetres)                |
| Im            | Rm1   | Rm2   | …    | Rmn                                  |
| (blank line)  |       |       |      |                                      |
|               | J1    | J2    | …    | Jn                                   |
| I1            | Rc11  | Rc12  | …    | Rc1n  Table of radii of curvature    |
| I2            | Rc21  | Rc22  | …    | Rc2n  of left- and right-hand sides  |
|  .            |   .   |   .   |   .  |   .  of each quadrilateral region    |
| Im            | Rcm1  | Rcm2  | …    | Rcmn  (in millimetres)               |
| (blank line)  |       |       |      |                                      |
|               | J1    | J2    | …    | Jn                                   |
| I1            | Rd11  | Rd12  | …    | Rd1n  Table of radii of curvature    |
| I2            | Rc21  | Rd22  | …    | Rd2n  of upper and lower sides       |
|  .            |   .   |   .   |   .  |   .  of each quadrilateral region    |
| Im            | Rdm1  | Rdm2  | …    | Rdmn  (in millimetres)               |
| (blank line)  |       |       |      |                                      |
| Ja1           | Jb1   | Ia1   | Ib1  | MU1                                  |
| Ja2           | Jb2   | Ia2   | Ib2  | MU2  Data specifying locations       |
|   .           |   .   |   .   |   .  |   .  and relative permeabilities     |
| Jak           | Jbk   | Iak   | Ibk  | MUk  of the polepieces               |
| (blank line)  |       |       |      |                                      |
| (blank line)  |       |       |      |                                      |
| I1            | VL1   |       |      |                                      |
|  .            |   .   |       |      |   Left hand boundary potentials      |
| Im            | VLm   |       |      |   (in Ampère-turns)                  |
| J1            | VU1   |       |      |                                      |
|  .            |   .   |       |      |   Upper boundary potentials          |
| Jn            | VUn   |       |      |   (in Ampère-turns)                  |
| I1            | VR1   |       |      |                                      |
|  .            |   .   |       |      |   Right hand boundary potentials     |
| Im            | VRm   |       |      |   (in Ampère-turns)                  |
| (blank line)  |       |       |      |                                      |
| (blank line)  |       |       |      |                                      |
Table 2.  General format of the data for Program SOMLENSP.
  Now write out the data as follows:

7. For the first line of data, write any title. This title will be printed at the top of the output.
8. For the second line of data, write 2 values:
N NSYM
N (which must be 0 or 1) specifies what output is required.
If N = 0, only the axial flux density distribution will be output.
If N = 1, the potentials at each mesh-point will also be output.
NSYM (which must be 0 or 1) specifies whether an asymmetric or a symmetrical lens
is being analysed.
NSYM = 0 signifies an asymmetric lens.
NSYM = 1 signifies a symmetrical lens.
(See the OPTICS User Manual for examples of asymmetric and symmetrical lenses.)
9. For the third line of data, write a blank line.
10. The next portion of the data is a table of values, specifying the axial coordinates of the mesh-points, in
millimetres. To start this table, write out, in a row across the page, the principal mesh-line numbers you
have chosen in the axial direction. Similarly, write out, in a column down the page, the principal mesh-line
numbers you have chosen on the left-hand boundary. Then complete this table, by specifying the z-
coordinates of each principal mesh-point, in millimetres.
11. Below the table of axial coordinates, write a blank line.
12. The next portion of the data is a table specifying the radial coordinates of each principal mesh-point. Its
format is the same as that for the axial coordinates.
13. Below the table of radial coordinates, write a blank line.
14. The next portion of the data is a table specifying the radii of curvature, in millimetres, of the mesh-lines
running from top to bottom of the mesh (e.g. line AB in Figure 13(a)). If the mesh-line is a straight line,
specify its radius of curvature as zero. If the mesh line has a curvature that is convex in the z-direction (e.g.
the line AB in Figure 13(a)), specify a positive value for the radius of curvature. If the mesh-line curvature
is concave in the z-direction, specify a negative value for the radius of curvature. The format of this portion
of the data is the same as that for the tables of axial and radial coordinates. The values on the last line of
this table should all be specified as zero (see Table 1).
15. Below this table of radii of curvature, write a blank line.
16. The next portion of the data is a table specifying the radii of curvature, in millimetres, of the mesh-lines
running from the left-hand side to the right-hand side of the mesh (e.g. line CD in Figure 13(a)). If the mesh-
line is a straight line, specify its radius of curvature as zero. If the mesh-line has a curvature that is convex
in the r-direction, specify a positive value for the radius of curvature. If the mesh-line curvature is concave
in the r-direction (e.g. line CD in Figure 13(a)), specify a negative value for the radius of curvature. The format of this portion of the data is the same as that for the tables of axial and radial coordinates. The values in the last column of this table should all be specified as zero (see Table 1).
17. Below this table of radii of curvature, write a blank line.
18. The next portion of data specifies the positions and relative permeability of the polepieces. To write out
this data, first partition the polepieces, if necessary, into quadrilateral sub-regions. Each region of a
polepiece is then specified by a line of data of the general form:
Ja Jb Ia Ib MU
Ja, Jb, Ia and Ib specify the mesh-line numbers by which the region is bounded, Ja being the smaller mesh-
line number in the axial direction, Jb the larger mesh-line number in the axial direction, Ia the smaller mesh-
line number in the radial direction, and Ib the larger mesh-line number in the radial direction. MU is the
relative permeability of the region.
19. After writing as many lines of data as are required to specify the polepieces, terminate this section of the
data by two blank lines.
20. The final portion of the data specifies the boundary potential distribution. This data is subdivided into three
sections:
The first section specifies the potentials on the left-hand boundary, running from top to bottom of the
mesh.
The second section specifies the potentials on the upper boundary, running from left to right of the
mesh.
The third section specifies the potentials on the right-hand boundary, running from top to bottom of
the mesh.
Each section of the boundary potentials data consists of several lines, of the form:
K1 V1
K2 V2
.. ..
.. ..
Kn Vn
K1, K2, ..., Kn are mesh-line numbers, and V1, V2, ...,Vn are the corresponding magnetic scalar potential
values at these mesh-points. On the boundaries, the program interpolates the potential linearly between
the mesh-points at which the potential values are explicitly specified.
21. Below the data specifying the boundary potential distribution, write two blank lines.
This completes the data preparation for Program SOMLENSP.
Before running Program SOMLENSP, you can check that the finite element mesh has been specified correctly,
by running Program SOPLOTM, which plots the mesh layout. (Refer to the SOPLOTM section of this manual for
details on how to run Program SOPLOTM.)
