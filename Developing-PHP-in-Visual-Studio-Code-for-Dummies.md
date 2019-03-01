  <div id="wiki-content" class="d-flex flex-column flex-md-row">
    <div id="wiki-body" class="mt-4 flex-auto min-width-0 gollum-markdown-content instapaper_body">
        <div class="markdown-body">
          <p>This article describes how to set up your tooling if you want a free and lightweight option for developing PHP projects on Windows.</p>
<h1>
<a id="user-content-install-php" class="anchor" href="#install-php" aria-hidden="true"><svg class="octicon octicon-link" viewbox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Install PHP</h1>
<ol>
<li>Download PHP from <a href="http://windows.php.net/download/" rel="nofollow">http://windows.php.net/download/</a>. I'm using the <code>VC14 x64 Non Thread Safe</code> version</li>
<li>Extract it to <code>c:\php</code>
</li>
<li>Copy contents of <code>php.ini-production</code> to <code>php.ini</code>
</li>
<li>Edit <code>php.ini</code> and uncomment <code>extension_dir = “ext”</code>
</li>
<li>Uncomment some basic extensions</li>
</ol>
<pre><code>extension=php_bz2.dll
extension=php_curl.dll
extension=php_fileinfo.dll
extension=php_gd2.dll
extension=php_intl.dll
extension=php_mbstring.dll
extension=php_exif.dll
extension=php_openssl.dll
</code></pre>
<h1>
<a id="user-content-install-xdebug" class="anchor" href="#install-xdebug" aria-hidden="true"><svg class="octicon octicon-link" viewbox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Install XDebug</h1>
<ol>
<li>Go to <code>c:\php</code>
</li>
<li>
<code>SHIFT</code>+<code>Right click</code> in the folder -&gt; <code>Open PowerShell window here</code>
</li>
<li>Run <code>php -i</code>
</li>
<li>Copy the output</li>
<li>Paste it here <a href="https://xdebug.org/wizard.php" rel="nofollow">https://xdebug.org/wizard.php</a> and follow the instructions which basically say:</li>
<li>Click download</li>
<li>Extract it to <code>C:\php\ext</code>
</li>
<li>Adjust <code>c:\php\php.ini</code>
The XDebug section can look like this:</li>
</ol>
<pre><code>[XDebug]
zend_extension = php_xdebug-2.5.4-7.1-vc14-nts-x86_64.dll
xdebug.default_enable = 1
xdebug.scream = 1
xdebug.coverage_enable = 1
xdebug.profiler_enable = 0
xdebug.profiler_enable_trigger = 1
xdebug.profiler_output_dir = "C:\php\profiles"
xdebug.remote_enable = 1
xdebug.remote_autostart  = 1
xdebug.remote_host=127.0.0.1
xdebug.remote_port = 9000
</code></pre>
<ol start="9">
<li>Add <code>c:\php</code> to your PATH environment variable</li>
<li>Add key: <code>XDEBUG_CONFIG</code> with value: <code>idekey=VSCODE</code> to your System Variables</li>
</ol>
<h1>
<a id="user-content-install-visual-studio-code" class="anchor" href="#install-visual-studio-code" aria-hidden="true"><svg class="octicon octicon-link" viewbox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Install Visual Studio Code</h1>
<ol>
<li>Download and install VS Code <a href="https://code.visualstudio.com/" rel="nofollow">https://code.visualstudio.com/</a>
</li>
<li>Learn <code>CTRL</code>+<code>SHIFT</code>+<code>P</code> to run any command (aka Command Palette)</li>
<li>Use the Command Palette shortcut and search for "Inst Ext"</li>
<li>Install Composer into your OS from <a href="https://getcomposer.org/doc/00-intro.md#installation-windows" rel="nofollow">https://getcomposer.org/doc/00-intro.md#installation-windows</a>
</li>
</ol>
<ul>
<li>You might experience error during installation, validate the <code>php_xdebug-XYZ.dll</code> file name from error is the same as in the <code>C:\php\ext</code> dir. Change name or config appropriately.</li>
</ul>
<ol start="5">
<li>Install the following extensions:</li>
</ol>
<ul>
<li>
<a href="https://marketplace.visualstudio.com/items?itemName=ikappas.composer" rel="nofollow">Composer</a>
<ul>
<li>You can also download it separately: <a href="https://getcomposer.org/download/" rel="nofollow">https://getcomposer.org/download/</a>
</li>
<li>You must set composer.executablePath user setting as:
<code>"composer.executablePath": "C:\\ProgramData\\ComposerSetup\\bin\\composer.bat"</code>
</li>
<li>You will be unable to use this plugin unless you configure this setting before first use.</li>
<li>Validate correct settings via <code>Composer: Validate</code>
</li>
</ul>
</li>
<li>
<a href="https://marketplace.visualstudio.com/items?itemName=emallin.phpunit" rel="nofollow">PHPUnit</a>
<ul>
<li>Can be installed also via Composer by running <code>composer global require phpunit/phpunit</code>
</li>
</ul>
</li>
<li><a href="https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-intellisense" rel="nofollow">PHP IntelliSense</a></li>
<li><a href="https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-debug" rel="nofollow">PHP Debug</a></li>
<li><a href="https://marketplace.visualstudio.com/items?itemName=DotJoshJohnson.xml" rel="nofollow">XML Tools</a></li>
</ul>
<ol start="6">
<li>Use the Command Palette to "Open User Settings"</li>
<li>Configure PHP-related settings</li>
</ol>
<pre><code>{
    "php.executablePath": "C:\\php\\php.exe",
    "php.validate.executablePath": "C:\\php\\php.exe",
    "php.validate.enable": true,
    "php.validate.run": "onType",
    "phpunit.execPath": "C:\\Users\\&lt;yourusername&gt;\\AppData\\Roaming\\Composer\\vendor\\bin\\phpunit.bat",
    "phpunit.args": [ ]
}
</code></pre>
<h1>
<a id="user-content-done" class="anchor" href="#done" aria-hidden="true"><svg class="octicon octicon-link" viewbox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Done</h1>
<p>You're ready to start coding in PHP!</p>
<p><a href="https://github.com/Kentico/delivery-sdk-php/wiki/Doing-PHP-stuff-on-Windows-with-VS-Code"><strong>Part 2: Continue reading about debugging, unit testing, autoloading, bootstrapping...</strong></a></p>
<h1>
<a id="user-content-more-resources" class="anchor" href="#more-resources" aria-hidden="true"><svg class="octicon octicon-link" viewbox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>More resources</h1>
<p>More detailed resources that helped me assemble this tutorial:</p>
<ul>
<li><a href="https://www.newmediacampaigns.com/blog/woah-i-switched-to-windows-and-its-awesome-for-php-development" rel="nofollow">Woah! I switched to Windows and it’s awesome for PHP development</a></li>
<li><a href="https://blogs.msdn.microsoft.com/nicktrog/2016/02/11/configuring-visual-studio-code-for-php-development/" rel="nofollow">Configuring Visual Studio Code for PHP development</a></li>
<li><a href="https://code.visualstudio.com/docs/languages/php" rel="nofollow">PHP Programming with VS Code</a></li>
<li><a href="https://github.com/elonmallin/vscode-phpunit">VS Code PHP Unit Extension Documentation</a></li>
<li><a href="https://github.com/felixfbecker/vscode-php-debug">VS Code PHP Debug Extension Documentation</a></li>
</ul>
<p><img src="https://camo.githubusercontent.com/6dabef870b324db8fd16195bedb9223c05b838a3/68747470733a2f2f6b656e7469636f2d67612d626561636f6e2e617a75726577656273697465732e6e65742f6170692f55412d36393031343236302d342f4b656e7469636f2f64656c69766572792d73646b2d7068702f77696b692f446576656c6f70696e672d5048502d696e2d56697375616c2d53747564696f2d436f64652d666f722d44756d6d6965733f706978656c" alt="Analytics" data-canonical-src="https://kentico-ga-beacon.azurewebsites.net/api/UA-69014260-4/Kentico/delivery-sdk-php/wiki/Developing-PHP-in-Visual-Studio-Code-for-Dummies?pixel"></p>

        </div>

    </div>

    <div id="wiki-rightbar" class="mt-4 ml-md-6 flex-shrink-0 width-full wiki-rightbar">
      <div id="wiki-pages-box" class="mb-4 wiki-pages-box js-wiki-pages-box" role="navigation">
        
<div class="Box Box--condensed box-shadow">
  <div class="Box-header js-wiki-toggle-collapse" style="cursor: pointer">
    <h3 class="Box-title">
      <svg class="octicon octicon-triangle-down js-wiki-sidebar-toggle-display" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M0 5l6 6 6-6H0z"/></svg>
      <svg class="octicon octicon-triangle-right js-wiki-sidebar-toggle-display d-none" viewBox="0 0 6 16" version="1.1" width="6" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M0 14l6-6-6-6v12z"/></svg>
      Pages <span class="Counter Counter--gray">8</span>
    </h3>
  </div>
  <div class=" js-wiki-sidebar-toggle-display">
    <div class="filter-bar">
      <input type="text" id="wiki-pages-filter" class="form-control input-sm input-block js-filterable-field" placeholder="Find a Page…" aria-label="Find a Page…">
    </div>

    <ul class="m-0 p-0 list-style-none" data-filterable-for="wiki-pages-filter" data-filterable-type="substring">
        <li class="Box-row">
          <strong><a class="d-block" href="/Kentico/delivery-sdk-php/wiki">Home</a></strong>
        </li>
        <li class="Box-row">
          <strong><a class="d-block" href="/Kentico/delivery-sdk-php/wiki/Configuring-PHP-Storm-on-Linux">Configuring PHP Storm on Linux</a></strong>
        </li>
        <li class="Box-row">
          <strong><a class="d-block" href="/Kentico/delivery-sdk-php/wiki/Developing-PHP-in-Visual-Studio-Code-for-Dummies">Developing PHP in Visual Studio Code for Dummies</a></strong>
        </li>
        <li class="Box-row">
          <strong><a class="d-block" href="/Kentico/delivery-sdk-php/wiki/Doing-PHP-stuff-on-Windows-with-VS-Code">Doing PHP stuff on Windows with VS Code</a></strong>
        </li>
        <li class="Box-row">
          <strong><a class="d-block" href="/Kentico/delivery-sdk-php/wiki/Generate-documentation-manually">Generate documentation manually</a></strong>
        </li>
        <li class="Box-row">
          <strong><a class="d-block" href="/Kentico/delivery-sdk-php/wiki/How-to-publish-new-release">How to publish new release</a></strong>
        </li>
        <li class="Box-row">
          <strong><a class="d-block" href="/Kentico/delivery-sdk-php/wiki/Resolving-content-items-and-components-in-Rich-text">Resolving content items and components in Rich text</a></strong>
        </li>
        <li class="Box-row">
          <strong><a class="d-block" href="/Kentico/delivery-sdk-php/wiki/Resolving-links-to-content-items">Resolving links to content items</a></strong>
        </li>
    </ul>
  </div>
</div>

      </div>


      <h5 class="mt-0 mb-2">Clone this wiki locally</h5>
      <div class="width-full input-group">
        <input
            id="wiki-clone-url"
            type="text"
            data-autoselect
            class="form-control input-sm text-small text-gray input-monospace"
            aria-label="Clone URL for this wiki"
            value="https://github.com/Kentico/delivery-sdk-php.wiki.git"
            readonly="readonly">
        <span class="input-group-button">
          <clipboard-copy for="wiki-clone-url" aria-label="Copy to clipboard" class="btn btn-sm zeroclipboard-button">
            <svg class="octicon octicon-clippy" viewBox="0 0 14 16" version="1.1" width="14" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M2 13h4v1H2v-1zm5-6H2v1h5V7zm2 3V8l-3 3 3 3v-2h5v-2H9zM4.5 9H2v1h2.5V9zM2 12h2.5v-1H2v1zm9 1h1v2c-.02.28-.11.52-.3.7-.19.18-.42.28-.7.3H1c-.55 0-1-.45-1-1V4c0-.55.45-1 1-1h3c0-1.11.89-2 2-2 1.11 0 2 .89 2 2h3c.55 0 1 .45 1 1v5h-1V6H1v9h10v-2zM2 5h8c0-.55-.45-1-1-1H8c-.55 0-1-.45-1-1s-.45-1-1-1-1 .45-1 1-.45 1-1 1H3c-.55 0-1 .45-1 1z"/></svg>
          </clipboard-copy>
        </span>
      </div>
    </div>
  </div>