# About

Add some information about your project here.

# Install Latest Version

You can use the button below to install the pre-built firmware directly to your device via USB from the browser.

<esp-web-install-button
      manifest="https://firmware.esphome.io/project-template/project-template/manifest.json">
    </esp-web-install-button>

<script type="module" src="https://unpkg.com/esp-web-tools@10/dist/web/install-button.js?module"></script>

<details>
  <summary>Install Specific Version</summary>
  Version: <input />
</details>

<script>
  function setVersion(version) {
    document.querySelector('h1#install_latest_version').innerHTML = `Install {{ site.title }} ${version}`;
    document.querySelector('esp-web-install-button').manifest = `https://firmware.esphome.io/project-template/project-template/${version}/manifest.json`;
  }

  document.querySelector('input').addEventListener('change', ev => {
    const version = ev.target.value;
    setVersion(version);
  });
  var urlParams = new URLSearchParams(window.location.search);
  if (urlParams.has('version')) {
    const version = urlParams.get('version');
    setVersion(version);
  }
</script>
