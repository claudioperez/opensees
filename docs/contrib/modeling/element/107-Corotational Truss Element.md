# Corotational Truss Element

<p>This command is used to construct a corotational truss element
object. There are two ways to construct a corotational truss element
object:</p>
<p>One way is to specify an area and a UniaxialMaterial identifier:</p>
<table>
<tbody>
<tr class="odd">
<td><p><strong>element corotTruss $eleTag $iNode $jNode $A $matTag
&lt;-rho $rho&gt; &lt;-cMass $cFlag&gt; &lt;-doRayleigh
$rFlag&gt;</strong></p></td>
</tr>
</tbody>
</table>
<p>the other is to specify a Section identifier:</p>
<table>
<tbody>
<tr class="odd">
<td><p><strong>element corotTrussSection $eleTag $iNode $jNode $secTag
&lt;-rho $rho&gt; &lt;-cMass $cFlag&gt; &lt;-doRayleigh
$rFlag&gt;</strong></p></td>
</tr>
</tbody>
</table>
<hr />
<table>
<tbody>
<tr class="odd">
<td><p><strong>$eleTag</strong></p></td>
<td><p>unique element object tag</p></td>
</tr>
<tr class="even">
<td><p><strong>$iNode $jNode</strong></p></td>
<td><p>end nodes</p></td>
</tr>
<tr class="odd">
<td><p><strong>$A</strong></p></td>
<td><p>cross-sectional area of element</p></td>
</tr>
<tr class="even">
<td><p><strong>$matTag</strong></p></td>
<td><p>tag associated with previously-defined UniaxialMaterial</p></td>
</tr>
<tr class="odd">
<td><p><strong>$secTag</strong></p></td>
<td><p>tag associated with previously-defined Section</p></td>
</tr>
<tr class="even">
<td><p><strong>$rho</strong></p></td>
<td><p>mass per unit length, optional, default = 0.0</p></td>
</tr>
<tr class="odd">
<td><p><strong>$cFlag</strong></p></td>
<td><p>consistent mass flag, optional, default = 0</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>cFlag = 0 lumped mass matrix (default)</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>cFlag = 1 consistent mass matrix</p></td>
</tr>
<tr class="even">
<td><p><strong>$rFlag</strong></p></td>
<td><p>Rayleigh damping flag, optional, default = 0</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>rFlag = 0 NO RAYLEIGH DAMPING (default)</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>rFlag = 1 include Rayleigh damping</p></td>
</tr>
</tbody>
</table>
<p>NOTE:</p>
<ul>
<li>When constructed with a UniaxialMaterial object, the corotational
truss element considers strain-rate effects, and is thus suitable for
use as a damping element.</li>
</ul>
<ul>
<li>The valid queries to a truss element when creating an
ElementRecorder object are 'axialForce,' 'stiff,' deformations,'
'material matArg1 matArg2...,' 'section sectArg1 sectArg2...' There will
be more queries after the interface for the methods involved have been
developed further.</li>
</ul>
<ul>
<li>For backward compatability the command <em>'element corotTruss
$eleTag $iNode $jNode $secTag</em> will still work and produce a
CorotTrussSection element.</li>
</ul>
<ul>
<li>CorotTruss DOES NOT include Rayleigh damping by default.</li>
</ul>
<p>EXAMPLE:</p>
<p>element truss 1 2 4 5.5 9; # truss element with tag 1 added between
nodes 2 and 4 with area 5.5 that uses material 9</p>
<hr />
<p>Code Developed by: <span style="color:blue"> Michael H. Scott,
Oregon State University </span></p>