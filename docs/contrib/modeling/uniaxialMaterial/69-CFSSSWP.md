# CFSSSWP

<p>This command is used to construct a uniaxialMaterial model that
simulates the hysteresis response (Shear strength-lateral Displacement)
of a Steel-Sheathed Cold-Formed Steel Shear Wall Panel (CFS-SWP). The
hysteresis model has smooth curves and takes into account the strength
and stiffness degradation, as well as pinching effect.</p>
<p>This uniaxialMaterial gives results in Newton and Meter units, for
strength and displacement, respectively.</p>
<p><span style="color:blue"> <strong>NOTE:</strong> before you use
this material make sure that you have downloaded the latest OpenSees
version.</p>
<table>
<tbody>
<tr class="odd">
<td><p><strong>uniaxialMaterial CFSSSWP $tag $height $width $fuf $fyf
$tf $Af $fus $fys $ts $np $ds $Vs $sc $dt $openingArea
$openingLength</strong></p></td>
</tr>
</tbody>
</table>
<hr />
<table>
<tbody>
<tr class="odd">
<td><p><strong>$matTag</strong></p></td>
<td><p>Integer identifier used to tag the material model</p></td>
</tr>
<tr class="even">
<td><p><strong>$height</strong></p></td>
<td><p>SWP’s height (mm)</p></td>
</tr>
<tr class="odd">
<td><p><strong>$width</strong></p></td>
<td><p>SWP’s width (mm)</p></td>
</tr>
<tr class="even">
<td><p><strong>$fuf</strong></p></td>
<td><p>Tensile strength of framing members (MPa)</p></td>
</tr>
<tr class="odd">
<td><p><strong>$fyf</strong></p></td>
<td><p>Yield strength of framing members (MPa)</p></td>
</tr>
<tr class="even">
<td><p><strong>$tf</strong></p></td>
<td><p>Framing thickness (mm)</p></td>
</tr>
<tr class="odd">
<td><p><strong>$Af</strong></p></td>
<td><p>Framing cross section area (mm²)</p></td>
</tr>
<tr class="even">
<td><p><strong>$fus</strong></p></td>
<td><p>Tensile strength of steel sheet sheathing (MPa)</p></td>
</tr>
<tr class="odd">
<td><p><strong>$fys</strong></p></td>
<td><p>Yield strength of steel sheet sheathing (MPa)</p></td>
</tr>
<tr class="even">
<td><p><strong>$ts</strong></p></td>
<td><p>Sheathing thickness (mm)</p></td>
</tr>
<tr class="odd">
<td><p><strong>$np</strong></p></td>
<td><p>Sheathing number (one or two sides sheathed)</p></td>
</tr>
<tr class="even">
<td><p><strong>$ds</strong></p></td>
<td><p>Screws diameter (mm)</p></td>
</tr>
<tr class="odd">
<td><p><strong>$Vs</strong></p></td>
<td><p>Screws shear strength (N)</p></td>
</tr>
<tr class="even">
<td><p><strong>$sc</strong></p></td>
<td><p>Screw spacing on the SWP perimeter (mm)</p></td>
</tr>
<tr class="odd">
<td><p><strong>$dt</strong></p></td>
<td><p>Anchor bolt’s diameter (mm)</p></td>
</tr>
<tr class="even">
<td><p><strong>$openingArea</strong></p></td>
<td><p>Total area of openings (mm²)</p></td>
</tr>
<tr class="odd">
<td><p><strong>$openingLength</strong></p></td>
<td><p>Cumulative length of openings (mm)</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>
<hr />
<p><strong>DESCRIPTION:</strong></p>
<p>The uniaxial hysteresis model of Cold-Formed Steel Shear Wall Panel
(CFS-SWP) consists of three parts: backbone curves of the hysteresis
loops (states 1 and 2), hysteresis criteria (unloading-reloading path:
states 3 and 4) (Fig.2) and deterioration criteria. The following
paragraphs will respectively introduce the terms of the three parts.</p>
<p>Maximum lateral shear strength and the associated displacement are
assessed using an analytical method for steel sheathed CFS SWP proposed
by Yanari N and Yu C (2013) which takes into account a wide range of
factors that affect the behaviour and strength of a CFS SWP, namely:
material properties, thickness and geometry of sheathing and framing,
spacing of studs, construction details such as size and spacing of
sheathing-to-framing connections. The associated displacement is
evaluated using the equation C2.1-1 given by AISI S213-07 code.</p>
<p>In addition to the envelope curve, the proposed hysteresis model
requires the introduction of parameters that define the strength and
stiffness deterioration, as well as the pinching effect under cyclic
loading. Compared to the monotonic test result, the hysteresis response
of CFS SWP exhibits strength deterioration; even if the displacement
associated to peak strength has not been reached yet. The stiffness
deterioration of the proposed model is positively related to strength
degraded degree, and is defined in a same way as the strength
deterioration.</p>
<p><img src="Model_parameters.jpg"
title="Fig. 1: Unloading-reloading paths of the proposed hysteresis model"
width="400"
alt="Fig. 1: Unloading-reloading paths of the proposed hysteresis model" />
<img src="Deterioration.png"
title="Fig. 2: Impact of hysteresis damage on shear strength-lateral displacement response"
width="400"
alt="Fig. 2: Impact of hysteresis damage on shear strength-lateral displacement response" /></p>
<p>In order to account for the overall lateral stiffness and strength of
the SWP, an equivalent simple non-linear zeroLength element connected to
rigid truss elements which transmit the force to the boundary studs that
resist the uniaxial tension and compression stress is used (Fig.3). This
modeling tip leads to a considerable reduction in terms of elements
number constituting the CFS SWP. The boundary members form a mechanism
and the lateral stiffness and strength are derived directly from the
zeroLength element. The CFS SWP details, as well as a schematic
representation of the finite element model are illustrated in Fig.3.</p>
<figure>
<img src="SWP.jpg"
title="Fig. 3: Cold-Formed Steel Shear Wall Panel details and equivalent OpenSees finite element model"
width="700"
alt="Fig. 3: Cold-Formed Steel Shear Wall Panel details and equivalent OpenSees finite element model" />
<figcaption aria-hidden="true">Fig. 3: Cold-Formed Steel Shear Wall
Panel details and equivalent OpenSees finite element model</figcaption>
</figure>
<hr />
<p><strong>EXAMPLES:</strong></p>
<p><a href="Cold-Formed_Steel_Steel_Sheathed_Shear_Wall_Panel_examples"
title="wikilink">Cold-Formed Steel Steel Sheathed Shear Wall Panel
examples</a></p>
<hr />
<p><strong>REFERENCES:</strong></p>
<p><a
href="http://www.sciencedirect.com/science/article/pii/S0263823115301026">Smail
Kechidi and Nouredine Bourahla, Deteriorating hysteresis model for
cold-formed steel shear wall panel based on its physical and mechanical
characteristics, Journal of Thin-Walled Structures (2016), pp.421-430.
<a
href="DOI:10.1016/j.tws.2015.09.022">DOI:10.1016/j.tws.2015.09.022</a>.</a></p>
<p>Smail Kechidi, Hysteresis model development for cold-formed steel
shear wall panel based on physical and mechanical characteristics,
Master Thesis, University of Blida 1, Algeria, 2014.</p>
<p>Smail Kechidi and N Bourahla, Deteriorating hysteresis model for
cold-formed steel shear wall panel based on physical and mechanical
characteristics, OpenSees Days Portugal 2014- OPD 2014, 3-4 July 2014,
Porto, Portugal.</p>
<p>L.N. Lowes, A. Altoontash, Modelling reinforced-concrete beam-column
joints subjected to cyclic loading, Journal of Structural Engineering,
129(12):1686-1697, 2003.</p>
<p>Yanagi N, Yu C. Effective strip method for the design of cold-formed
steel framed shear wall with steel sheet sheathing. Journal of
Structural Engineering, ASCE 2014; 140(4).</p>
<p>Nisreen Balh, Development of seismic design provisions for steel
sheathed shear walls, Master Thesis, McGill University, Canada,
2010.</p>
<hr />
<p>Code Developed by: <span style="color:blue"> Smail Kechidi and
Nouredine Bourahla, University of Blida 1, Algeria </span></p>
<p>Images Developed by: <span style="color:blue"> Smail Kechidi,
University of Blida 1, Algeria </span></p>
<hr />
<p>Authors contact:</p>
<p><strong>Smail Kechidi</strong>, PhD student at University of Blida 1,
Algeria, s_kechidi@univ-blida.dz, skechidi@yahoo.com</p>
<p><strong>Nouredine Bourahla</strong>, Professor at University of Blida
1, Algeria, nbourahla@univ-blida.dz</p>