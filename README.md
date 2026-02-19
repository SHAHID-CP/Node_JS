# Node_JS
__Amra Node Js er Maddome Javascript code run kori ---------exm: node index.js =result__


##File System

<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Priority</th>
<th>Function</th>
<th>Description</th>
<th>Notes / Pro Tips</th>
</tr>
</thead>
<tbody>
<tr>
<td>⭐⭐⭐⭐⭐</td>
<td><code>fs.readFile</code> / <code>fs.promises.readFile</code></td>
<td>File read</td>
<td>Always handle encoding. Streams better for big files.</td>
</tr>
<tr>
<td>⭐⭐⭐⭐⭐</td>
<td><code>fs.writeFile</code> / <code>fs.promises.writeFile</code></td>
<td>File write</td>
<td>Overwrites by default. Use <code>fs.appendFile</code> if append needed.</td>
</tr>
<tr>
<td>⭐⭐⭐⭐</td>
<td><code>fs.appendFile</code> / <code>fs.promises.appendFile</code></td>
<td>Append data to file</td>
<td>Useful for logging.</td>
</tr>
<tr>
<td>⭐⭐⭐⭐</td>
<td><code>fs.unlink</code> / <code>fs.promises.unlink</code></td>
<td>Delete a file</td>
<td>Always check existence first.</td>
</tr>
<tr>
<td>⭐⭐⭐</td>
<td><code>fs.rename</code> / <code>fs.promises.rename</code></td>
<td>Rename or move file</td>
<td>Can move across folders.</td>
</tr>
<tr>
<td>⭐⭐⭐</td>
<td><code>fs.mkdir</code> / <code>fs.promises.mkdir</code></td>
<td>Make directories</td>
<td><code>{ recursive: true }</code> for nested dirs.</td>
</tr>
<tr>
<td>⭐⭐⭐</td>
<td><code>fs.rmdir</code> / <code>fs.promises.rmdir</code></td>
<td>Remove directories</td>
<td>Deprecated, use <code>fs.rm(dir, { recursive: true })</code>.</td>
</tr>
<tr>
<td>⭐⭐⭐⭐</td>
<td><code>fs.stat</code> / <code>fs.promises.stat</code></td>
<td>Get file info</td>
<td>Size, type, timestamps, permissions.</td>
</tr>
<tr>
<td>⭐⭐</td>
<td><code>fs.existsSync</code> / <code>fs.access</code></td>
<td>Check existence or permissions</td>
<td><code>fs.access</code> is async-safe.</td>
</tr>
<tr>
<td>⭐⭐⭐</td>
<td><code>fs.readdir</code> / <code>fs.promises.readdir</code></td>
<td>List directory contents</td>
<td>Can filter by file type.</td>
</tr>
<tr>
<td>⭐⭐⭐⭐</td>
<td><code>fs.createReadStream</code></td>
<td>Stream read large files</td>
<td>Use with pipe, memory efficient.</td>
</tr>
<tr>
<td>⭐⭐⭐⭐</td>
<td><code>fs.createWriteStream</code></td>
<td>Stream write large files</td>
<td>Good for uploads, logs.</td>
</tr>
<tr>
<td>⭐⭐</td>
<td><code>fs.watch</code></td>
<td>Watch file/folder changes</td>
<td>Can be flaky on some OS; consider <code>chokidar</code>.</td>
</tr>
<tr>
<td>⭐</td>
<td><code>fs.copyFile</code> / <code>fs.promises.copyFile</code></td>
<td>Copy files</td>
<td>Simple, no recursive dir copy.</td>
</tr>
</tbody>
</table>
