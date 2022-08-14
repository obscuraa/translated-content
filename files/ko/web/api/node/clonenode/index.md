---
title: Node.cloneNode()
slug: Web/API/Node/cloneNode
translation_of: Web/API/Node/cloneNode
---
<div>{{APIRef("DOM")}}</div>

<div><strong><code>Node.cloneNode()</code></strong> 메서드는 이 메서드를 호출한 Node 의 복제된 Node를 반환합니다.</div>

<h2 id="Syntax">Syntax</h2>

<pre class="syntaxbox">var <em><var>dupNode</var></em> = <em><var>node</var></em>.cloneNode(<em><var>deep</var></em>);
</pre>

<dl>
 <dt><em>node</em></dt>
 <dd>복제되어야 할 node.</dd>
 <dt><em>dupNode</em></dt>
 <dd><em>복제된 새로운 node.</em></dd>
 <dt><em>deep {{optional_inline}}</em></dt>
 <dd><em>해당 node의 children 까지 복제하려면 true, 해당 node 만 복제하려면 false</em></dd>
</dl>

<div class="note">
<p><strong>Note:</strong> In the DOM4 specification (as implemented in Gecko 13.0 {{geckoRelease(13)}}), <code>deep</code> is an optional argument. If omitted, the method acts as if the value of <code>deep</code> was <strong><code>true</code></strong>, defaulting to using deep cloning as the default behavior. To create a shallow clone, <code>deep</code> must be set to <code>false</code>.</p>

<p>This behavior has been changed in the latest spec, and if omitted, the method will act as if the value of <code>deep</code> was <strong><code>false</code></strong>. Though It's still optional, you should always provide the <code>deep</code> argument both for backward and forward compatibility. With Gecko 28.0 {{geckoRelease(28)}}), the console warned developers not to omit the argument. Starting with Gecko 29.0 {{geckoRelease(29)}}), a shallow clone is defaulted instead of a deep clone.</p>
</div>

<h2 id="Example">Example</h2>

<pre class="brush: js">var p = document.getElementById("para1");
var p_prime = p.cloneNode(true);
</pre>

<h2 id="Notes">Notes</h2>

<p id="not-event-listeners">Cloning a node copies all of its attributes and their values, including intrinsic (in–line) listeners. It does not copy event listeners added using <a href="/en-US/docs/DOM/element.addEventListener"><code>addEventListener()</code></a> or those assigned to element properties. (e.g. <code>node.onclick = fn</code>) Moreover, for a &lt;canvas&gt; element, the painted image is not copied.</p>

<p>The duplicate node returned by <code>cloneNode()</code> is not part of the document until it is added to another node that is part of the document using {{domxref("Node.appendChild()")}} or a similar method. It also has no parent until it is appended to another node.</p>

<p>If <code>deep</code> is set to <code>false</code>, child nodes are not cloned. Any text that the node contains is not cloned either, as it is contained in one or more child {{domxref("Text")}} nodes.</p>

<p>If <code>deep</code> evaluates to <code>true</code>, the whole subtree (including text that may be in child {{domxref("Text")}} nodes) is copied too. For empty nodes (e.g. {{HTMLElement("img")}} and {{HTMLElement("input")}} elements) it doesn't matter whether <code>deep</code> is set to <code>true</code> or <code>false</code>.</p>

<div class="warning"><strong>Warning:</strong> <code>cloneNode()</code> may lead to duplicate element IDs in a document.</div>

<p>If the original node has an ID and the clone is to be placed in the same document, the ID of the clone should be modified to be unique. Name attributes may need to be modified also, depending on whether duplicate names are expected.</p>

<p>To clone a node for appending to a different document, use {{domxref("Document.importNode()")}} instead.</p>

<h2 id="Specifications">Specifications</h2>

{{Specifications}}

<h2 id="Browser_compatibility">Browser compatibility</h2>

<p>{{Compat("api.Node.cloneNode")}}</p>