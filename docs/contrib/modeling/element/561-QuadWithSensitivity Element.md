# QuadWithSensitivity Element

<dl>
<dt></dt>
<dd>
This command is used to construct a 2D four-node quadrilateral element
object based on a bilinear isoparametric formulation.
</dd>
</dl>
<table>
<tbody>
<tr class="odd">
<td><p><strong>element quadWithSensitivity $eleTag $iNode $jNode $kNode
$lNode $thick $type $matTag &lt;$pressure $rho $b1
$b2&gt;</strong></p></td>
</tr>
</tbody>
</table>
<hr />
<table>
<tbody>
<tr class="odd">
<td><p><strong>$tag</strong></p></td>
<td><p>integer tag identifying an existing parameter.</p></td>
</tr>
<tr class="even">
<td><p><strong>$iNode $jnode $kNode $lNode</strong></p></td>
<td><p>four nodes defining element boundaries (numbered following a
counter-clockwise order around the element).</p></td>
</tr>
<tr class="odd">
<td><p><strong>$thick</strong></p></td>
<td><p>element thickness (constant).</p></td>
</tr>
<tr class="even">
<td><p><strong>$type</strong></p></td>
<td><p>string representing material behavior. Valid options depend on
the nDMaterial object and the corresponding available material
formulations. The ‘type’ parameter can be either "PlaneStrain" or
"PlaneStress".</p></td>
</tr>
<tr class="odd">
<td><p><strong>$matTag</strong></p></td>
<td><p>tag associated with previously-defined NDMaterial
object.</p></td>
</tr>
<tr class="even">
<td><p><strong>$pressure</strong></p></td>
<td><p>surface pressure (set temporarily equal to zero for DDM-based
sensitivity analysis).</p></td>
</tr>
<tr class="odd">
<td><p><strong>$rho</strong></p></td>
<td><p>element mass density (per unit volume) from which a lumped
element mass matrix is computed (optional, default=0.0).</p></td>
</tr>
<tr class="even">
<td><p><strong>$b1 $b2</strong></p></td>
<td><p>constant body forces defined in the isoparametric domain
(optional, default=0.0).</p></td>
</tr>
</tbody>
</table>
<hr />
<dl>
<dt></dt>
<dd>
All parameters are the same as those in the ‘quad’ element command.
Currently there are no sensitivity parameters in the
‘quadWithSensitivity’ element command.
</dd>
</dl>