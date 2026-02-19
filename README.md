# Node_JS
__Amra Node Js er Maddome Javascript code run kori ---------exm: node index.js =result__


## File System

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

<h2 class="code-line" data-line-start=0 data-line-end=1 ><a id="File_Operation_0"></a>File Operation</h2>
<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Method</th>
<th>Sync</th>
<th>Promise</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>readFile</code></td>
<td><code>readFileSync</code></td>
<td><code>fs.promises.readFile</code></td>
<td>পুরো ফাইল read করে buffer/string দেয়</td>
</tr>
<tr>
<td><code>writeFile</code></td>
<td><code>writeFileSync</code></td>
<td><code>fs.promises.writeFile</code></td>
<td>ফাইল write (overwrite করে)</td>
</tr>
<tr>
<td><code>appendFile</code></td>
<td><code>appendFileSync</code></td>
<td><code>fs.promises.appendFile</code></td>
<td>ফাইলের শেষে data যোগ করে</td>
</tr>
<tr>
<td><code>truncate</code></td>
<td><code>truncateSync</code></td>
<td><code>fs.promises.truncate</code></td>
<td>ফাইলের size কমায়</td>
</tr>
<tr>
<td><code>copyFile</code></td>
<td><code>copyFileSync</code></td>
<td><code>fs.promises.copyFile</code></td>
<td>ফাইল copy করে</td>
</tr>
<tr>
<td><code>rename</code></td>
<td><code>renameSync</code></td>
<td><code>fs.promises.rename</code></td>
<td>ফাইল rename/move করে</td>
</tr>
<tr>
<td><code>unlink</code></td>
<td><code>unlinkSync</code></td>
<td><code>fs.promises.unlink</code></td>
<td>ফাইল delete করে</td>
</tr>
<tr>
<td><code>open</code></td>
<td><code>openSync</code></td>
<td><code>fs.promises.open</code></td>
<td>ফাইল descriptor open করে</td>
</tr>
<tr>
<td><code>close</code></td>
<td><code>closeSync</code></td>
<td>—</td>
<td>descriptor close করে</td>
</tr>
</tbody>
</table>

<h2 class="code-line" data-line-start=0 data-line-end=1 ><a id="Directory_Operation_0"></a>Directory Operation</h2>
<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Method</th>
<th>Sync</th>
<th>Promise</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>mkdir</code></td>
<td><code>mkdirSync</code></td>
<td><code>fs.promises.mkdir</code></td>
<td>directory create</td>
</tr>
<tr>
<td><code>mkdtemp</code></td>
<td><code>mkdtempSync</code></td>
<td><code>fs.promises.mkdtemp</code></td>
<td>temp directory create</td>
</tr>
<tr>
<td><code>readdir</code></td>
<td><code>readdirSync</code></td>
<td><code>fs.promises.readdir</code></td>
<td>directory list</td>
</tr>
<tr>
<td><code>rmdir</code> (deprecated)</td>
<td><code>rmdirSync</code></td>
<td><code>fs.promises.rmdir</code></td>
<td>directory remove</td>
</tr>
<tr>
<td><code>rm</code></td>
<td><code>rmSync</code></td>
<td><code>fs.promises.rm</code></td>
<td>file বা directory remove</td>
</tr>
<tr>
<td><code>opendir</code></td>
<td><code>opendirSync</code></td>
<td><code>fs.promises.opendir</code></td>
<td>directory stream open</td>
</tr>
</tbody>
</table>
