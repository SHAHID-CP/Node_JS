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

<h2 class="code-line" data-line-start=0 data-line-end=1 ><a id="File_info__Meta_data_0"></a>File info / Meta data</h2>
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
<td><code>stat</code></td>
<td><code>statSync</code></td>
<td><code>fs.promises.stat</code></td>
<td>file info (size, time, type)</td>
</tr>
<tr>
<td><code>lstat</code></td>
<td><code>lstatSync</code></td>
<td><code>fs.promises.lstat</code></td>
<td>symlink info</td>
</tr>
<tr>
<td><code>fstat</code></td>
<td><code>fstatSync</code></td>
<td>—</td>
<td>descriptor info</td>
</tr>
<tr>
<td><code>access</code></td>
<td><code>accessSync</code></td>
<td><code>fs.promises.access</code></td>
<td>permission check</td>
</tr>
<tr>
<td><code>exists</code> (deprecated)</td>
<td>—</td>
<td>—</td>
<td>use <code>access</code> instead</td>
</tr>
<tr>
<td><code>chmod</code></td>
<td><code>chmodSync</code></td>
<td><code>fs.promises.chmod</code></td>
<td>permission change</td>
</tr>
<tr>
<td><code>chown</code></td>
<td><code>chownSync</code></td>
<td><code>fs.promises.chown</code></td>
<td>ownership change</td>
</tr>
<tr>
<td><code>utimes</code></td>
<td><code>utimesSync</code></td>
<td><code>fs.promises.utimes</code></td>
<td>timestamps change</td>
</tr>
</tbody>
</table>
<h2 class="code-line" data-line-start=12 data-line-end=13 ><a id="Link__Special_file_12"></a>Link &amp; Special file</h2>
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
<td><code>link</code></td>
<td><code>linkSync</code></td>
<td><code>fs.promises.link</code></td>
<td>hard link create</td>
</tr>
<tr>
<td><code>symlink</code></td>
<td><code>symlinkSync</code></td>
<td><code>fs.promises.symlink</code></td>
<td>symbolic link create</td>
</tr>
<tr>
<td><code>readlink</code></td>
<td><code>readlinkSync</code></td>
<td><code>fs.promises.readlink</code></td>
<td>symlink target read</td>
</tr>
<tr>
<td><code>realpath</code></td>
<td><code>realpathSync</code></td>
<td><code>fs.promises.realpath</code></td>
<td>absolute resolved path</td>
</tr>
</tbody>
</table>
<h2 class="code-line" data-line-start=20 data-line-end=21 ><a id="Streams_20"></a>Streams</h2>
<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Method</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>createReadStream</code></td>
<td>large file read stream</td>
</tr>
<tr>
<td><code>createWriteStream</code></td>
<td>large file write stream</td>
</tr>
</tbody>
</table>
<h2 class="code-line" data-line-start=26 data-line-end=27 ><a id="Watcher_26"></a>Watcher</h2>
<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Method</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>watch</code></td>
<td>file বা directory watch</td>
</tr>
<tr>
<td><code>watchFile</code></td>
<td>polling-based watch</td>
</tr>
<tr>
<td><code>unwatchFile</code></td>
<td>stop watching</td>
</tr>
</tbody>
</table>
