---


---

<h1 id="mongodb">MongoDB</h1>
<ul>
<li><strong>Document</strong> database.</li>
<li>Stores data in a type of JSON format called <strong>BSON</strong>.</li>
</ul>
<h2 id="terms">Terms</h2>

<table>
<thead>
<tr>
<th>SQL</th>
<th>MongoDB</th>
</tr>
</thead>
<tbody>
<tr>
<td>Tables</td>
<td>Collections</td>
</tr>
<tr>
<td>Records</td>
<td>Documents</td>
</tr>
<tr>
<td>Columns</td>
<td>Fields</td>
</tr>
<tr>
<td>Index</td>
<td>Index</td>
</tr>
<tr>
<td>Table Joins</td>
<td><code>$lookup</code></td>
</tr>
</tbody>
</table><h2 id="sql-vs.-document-databases">SQL vs. Document Databases</h2>
<ul>
<li>SQL databases are relational databases. They store related data in separate tables. It is quried from multiple tables to join the data back together.</li>
<li>Document databases, also known as non-relational or non-tabular databases, store related data in flexible documents. They keep all related data together, which makes reading data very fast.</li>
</ul>
<h2 id="commands">Commands</h2>

<table>
<thead>
<tr>
<th>Description</th>
<th>Command</th>
</tr>
</thead>
<tbody>
<tr>
<td>Get Available Databases</td>
<td><code>show dbs</code></td>
</tr>
<tr>
<td>Create Database</td>
<td><code>use xxx</code></td>
</tr>
<tr>
<td>Create Collection</td>
<td>- <code>db.createCollection('xxx')</code> - <code>db.xxx.insertOne(object)</code></td>
</tr>
<tr>
<td>Insert Single Document</td>
<td><code>db.xxx.insertOne(object)</code></td>
</tr>
<tr>
<td>Insert Multiple Documents</td>
<td><code>db.xxx.insertMany(object[])</code></td>
</tr>
<tr>
<td>Get Single (First) Document</td>
<td><code>db.xxx.findOne()</code></td>
</tr>
<tr>
<td>Get Documents</td>
<td><code>db.xxx.find()</code></td>
</tr>
<tr>
<td>Update Single (First) Document</td>
<td><code>db.xxx.updateOne({filter}, {$set: {updatedObject})</code></td>
</tr>
<tr>
<td>Update Multiple Documents</td>
<td><code>db.xxx.updateMany({filter}, {operator})</code></td>
</tr>
<tr>
<td>Delete Single (First Document)</td>
<td><code>db.xxx.deleteOne({filter})</code></td>
</tr>
<tr>
<td>Delete Multiple Documents</td>
<td><code>db.xxx.deleteMany({filter})</code></td>
</tr>
</tbody>
</table><h2 id="projection">Projection</h2>
<ul>
<li><code>db.xxx.find()</code> and <code>db.xxx.findOne()</code> accept a second parameter called <code>projection</code>.</li>
<li>It is an object that describes which <strong>fields to include</strong> in the results.</li>
<li>It is optional.</li>
<li><code>1</code> to include a field; <code>0</code> to exclude a field.</li>
<li>Cannot use both <code>0</code> and <code>1</code> in the same object. Only exception is the <code>_id</code> field. For example, <code>db.xxx.find({}, {title: 1, date: 0})</code>.</li>
</ul>
<h2 id="update-documents">Update Documents</h2>
<ul>
<li><code>{upsert: true}</code> to insert the document if it is not found.</li>
</ul>
<h2 id="query-operators">Query Operators</h2>
<h3 id="comparison">Comparison</h3>

<table>
<thead>
<tr>
<th>Description</th>
<th>Operator</th>
</tr>
</thead>
<tbody>
<tr>
<td>Equal</td>
<td><code>$eq</code></td>
</tr>
<tr>
<td>Not Equal</td>
<td><code>$ne</code></td>
</tr>
<tr>
<td>Greater Than</td>
<td><code>$gt</code></td>
</tr>
<tr>
<td>Greater Than or Equal</td>
<td><code>$gte</code></td>
</tr>
<tr>
<td>Less Than</td>
<td><code>$lt</code></td>
</tr>
<tr>
<td>Less Than or Equal</td>
<td><code>$lte</code></td>
</tr>
<tr>
<td>Matched within Array</td>
<td><code>$in</code></td>
</tr>
</tbody>
</table><h3 id="logical">Logical</h3>

<table>
<thead>
<tr>
<th>Description</th>
<th>Operator</th>
</tr>
</thead>
<tbody>
<tr>
<td>Both Queries Match</td>
<td><code>$and</code></td>
</tr>
<tr>
<td>Either Query Matches</td>
<td><code>$or</code></td>
</tr>
<tr>
<td>Both Queries Not Match</td>
<td><code>$nor</code></td>
</tr>
<tr>
<td>Query Not Match</td>
<td><code>$not</code></td>
</tr>
</tbody>
</table><h3 id="evaluation">Evaluation</h3>

<table>
<thead>
<tr>
<th>Description</th>
<th>Operator</th>
</tr>
</thead>
<tbody>
<tr>
<td>Regrex when Evaluating</td>
<td><code>$regrex</code></td>
</tr>
<tr>
<td>Text Search</td>
<td><code>$text</code></td>
</tr>
<tr>
<td>JavaScript to Match Documents</td>
<td><code>$where</code></td>
</tr>
</tbody>
</table><h2 id="update-operators">Update Operators</h2>
<h3 id="fields">Fields</h3>

<table>
<thead>
<tr>
<th>Description</th>
<th>Operator</th>
</tr>
</thead>
<tbody>
<tr>
<td>Current Data</td>
<td><code>$currentData</code></td>
</tr>
<tr>
<td>Increment</td>
<td><code>$inc</code></td>
</tr>
<tr>
<td>Rename</td>
<td><code>$rename</code></td>
</tr>
<tr>
<td>Set Value</td>
<td><code>$set</code></td>
</tr>
<tr>
<td>Remove Fields</td>
<td><code>$unset</code></td>
</tr>
</tbody>
</table><h3 id="array">Array</h3>

<table>
<thead>
<tr>
<th>Description</th>
<th>Operator</th>
</tr>
</thead>
<tbody>
<tr>
<td>Add Distinct Elements</td>
<td><code>$addToSet</code></td>
</tr>
<tr>
<td>Remove First or Last Element</td>
<td><code>$pop</code></td>
</tr>
<tr>
<td>Remove All Elements with Matched Query</td>
<td><code>$pull</code></td>
</tr>
<tr>
<td>Add An Element<code>$push</code></td>
<td></td>
</tr>
</tbody>
</table>
