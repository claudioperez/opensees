# Standard Brick

This element is used to construct an eight-node brick element object,
which uses a trilinear isoparametric formulation.

```tcl
element stdBrick $eleTag $node1 $node2 $node3 $node4
        $node5 $node6 $node7 $node8 $matTag  < $b1 $b2 $b3 >
```

<hr />
<table>
<tbody>
<tr class="odd">
<td><code class="parameter-table-variable">eleTag</code></td>
<td><p>unique element object tag</p></td>
</tr>
<tr class="even">
<td><p><code>node1 node2</code></p>
<p><code>node3 node4</code></p>
<p><code>node5 node6</code></p>
<p><code>node7 node8</code></p></td>
<td><p>eight nodes defining element boundaries, input order is shown in
the figure.</p></td>
</tr>
<tr class="odd">
<td><code class="parameter-table-variable">matTag</code></td>
<td><p>tag of nDMaterial</p></td>
</tr>
<tr class="even">
<td><p><code>b1 b2 b3</code></p></td>
<td><p>body forces in global $x$,$y$,$z$ directions</p></td>
</tr>
</tbody>
</table>
<figure>
<img src="/OpenSeesRT/contrib/static/Brick.gif" title="Brick.gif" alt="Brick.gif" />
<figcaption aria-hidden="true">Brick.gif</figcaption>
</figure>
<p>NOTE:</p>
<ol>
<li>The valid queries to a Brick element when creating an
  `ElementRecorder` are `forces`, `stresses`, (`strains` version &gt;
  2.2.0) and `material $matNum matArg1 matArg2 ...` Where $matNum refers
  to the material object at the integration point corresponding to the
  node numbers in the isoparametric domain.</li>
<li>This element can only be defined in `-ndm 3 -ndf 3`</li>
</ol>

## Examples

## References
<hr />
<p>Code Developed by: <span style="color:blue"> Edward Love,
Sandia National Laboratories </span></p>
