<script>
  import { SvelteToast, toast } from "@zerodevx/svelte-toast";

  export let first_name = "First";
  export let last_name = "Last";
  export let title = "Title/Position";
  export let phone = "000-000-0000";
  export let mobile_phone = "000-000-0000";
  export let email = "[email]@thunderbiotech.com";

  function selectText() {
    const node = document.querySelector(".result table");

    if (document.body.createTextRange) {
      const range = document.body.createTextRange();
      range.moveToElementText(node);
      range.select();
    } else if (window.getSelection) {
      const selection = window.getSelection();
      const range = document.createRange();
      range.selectNodeContents(node);
      selection.removeAllRanges();
      selection.addRange(range);
    } else {
      console.warn("Could not select text in node: Unsupported browser.");
    }
  }

  function copyHtml() {
    const html = document.querySelector(".result table").outerHTML;
    navigator.clipboard.writeText(html).then(
      function () {
        toast.push(
          "HTML copied to clipboard. You can paste it whereever you would like.",
          {
            theme: {
              "--toastBackground": "#10B981",
              "--toastColor": "white",
              "--toastProgressBackground": "#047857",
            },
          }
        );
      },
      function (err) {
        toast.push(
          "There was an error copying the HTML to your clipboard. Either view the source on this page, or copy the section of the page above manually.",
          {
            theme: {
              "--toastBackground": "#EF4444",
              "--toastColor": "white",
              "--toastProgressBackground": "#B91C1C",
            },
          }
        );
      }
    );
  }
</script>

<SvelteToast />

<main>
  <h1>Thunder Biotech Email Generator</h1>
  <div class="container">
    <form>
      <div>
        <label for="first_name">First Name</label>
        <input type="text" name="first_name" bind:value={first_name} />
      </div>
      <div>
        <label for="last_name">Last Name</label>
        <input type="text" name="last_name" bind:value={last_name} />
      </div>
      <div>
        <label for="title">Title</label>
        <input type="text" name="title" bind:value={title} />
      </div>
      <div>
        <label for="phone">Direct Phone</label>
        <input type="text" name="phone" bind:value={phone} />
      </div>
      <div>
        <label for="mobile_phone">Mobile Phone</label>
        <input type="text" name="mobile_phone" bind:value={mobile_phone} />
      </div>
      <div>
        <label for="email">Email</label>
        <input type="email" name="email" bind:value={email} />
      </div>
    </form>

    <div>
      <h2>Result</h2>
      <div class="result">
        <table
          style="color: #4c4d4e; font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, 'Noto Sans', sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';"
        >
          <tr>
            <td style="border-right: 2px solid #83beb1; padding-right: 80px">
              <p style="font-size: 24px; color: #4c4d4e; margin: 0;">
                <strong style="font-weight: 500"
                  >{first_name} {last_name}</strong
                >
              </p>
              <p
                style="font-size: 20px; font-weight: 300; color:#83beb1; margin: 7px 0 20px 0;"
              >
                {title}
              </p>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 78 8.05"
                style="width: 200px"
              >
                <path
                  style="fill: #83beb1"
                  d="M50.72,49.66a2.76,2.76,0,1,1,2.76,2.84A2.7,2.7,0,0,1,50.72,49.66Zm4.3,0a1.55,1.55,0,1,0-1.54,1.73A1.56,1.56,0,0,0,55,49.66Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #477c7c"
                  d="M2.16,45.79H0V44.52H5.73v1.27H3.56V52.4H2.16Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #477c7c"
                  d="M11.5,49.27V52.4H10.1V49.5a1.09,1.09,0,0,0-1.16-1.23c-.72,0-1.24.45-1.24,1.4V52.4H6.3V44.6H7.7v3A2.25,2.25,0,0,1,9.35,47,2,2,0,0,1,11.5,49.27Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #477c7c"
                  d="M17.53,46.89V52.4H16.32v-.62a2.54,2.54,0,0,1-1.81.71,2.05,2.05,0,0,1-2.18-2.35V46.89h1.4v3c0,.87.46,1.26,1.12,1.26a1.24,1.24,0,0,0,1.27-1.41V46.89Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #477c7c"
                  d="M30.27,44.59V52.4H29.05v-.6a2.32,2.32,0,0,1-1.78.68,2.75,2.75,0,0,1-2.65-2.89,2.56,2.56,0,0,1,2.65-2.67,2.13,2.13,0,0,1,1.6.68v-3Zm-1.42,5.22a1.69,1.69,0,0,0-1.53-1.66A1.32,1.32,0,0,0,26,49.59a1.55,1.55,0,0,0,1.38,1.65A1.44,1.44,0,0,0,28.85,49.81Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #83beb1"
                  d="M47.07,50.15a2.34,2.34,0,0,1-2.38,2.26h-3.5V44.6h3.3c1.69,0,2.56,1,2.56,2.08a2.56,2.56,0,0,1-.68,1.82A2.31,2.31,0,0,1,47.07,50.15Zm-4.46-4.38v2.16H44.3c.91,0,1.44-.32,1.44-1.06s-.49-1.1-1.44-1.1Zm0,3.38V51.3H44.3c.91,0,1.44-.32,1.44-1s-.49-1.1-1.44-1.1Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #83beb1"
                  d="M48.18,45.37a.78.78,0,0,1,.82-.79.76.76,0,0,1,.82.76.82.82,0,0,1-1.64,0Z"
                  transform="translate(0 -44.45)"
                /><rect
                  style="fill: #83beb1"
                  x="48.3"
                  y="2.43"
                  width="1.4"
                  height="5.51"
                /><path
                  style="fill: #83beb1"
                  d="M60.73,52.22a1.41,1.41,0,0,1-1,.26,1.7,1.7,0,0,1-1.93-1.86V48H56.67V46.84H57.8V44.45h1.4v2.39h1.39V48H59.18v2.6a.6.6,0,0,0,.65.68,1.77,1.77,0,0,0,.53-.05Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #83beb1"
                  d="M72,51.66l0,0a2.67,2.67,0,0,1-1.53.77l-.2,0h-.2a2.83,2.83,0,1,1,0-5.66h.2l.2,0a2.67,2.67,0,0,1,1.53.77l0,0-.75.9a1.75,1.75,0,0,0-.67-.36,1.73,1.73,0,0,0-.54-.08,1.41,1.41,0,0,0-1,.43l0,.05-.08.09,0,.06,0,.07a.77.77,0,0,0-.1.18,1.07,1.07,0,0,0-.07.19.74.74,0,0,0,0,.14.88.88,0,0,0,0,.16,1.45,1.45,0,0,0,0,.34.88.88,0,0,0,0,.16.74.74,0,0,0,0,.14,1.07,1.07,0,0,0,.07.19,1,1,0,0,0,.1.18l0,.07,0,.06.08.09,0,.05a1.41,1.41,0,0,0,1,.43,1.81,1.81,0,0,0,.54-.08,1.75,1.75,0,0,0,.67-.36Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #83beb1"
                  d="M78,49.42v3H76.6V49.66c0-1.16-.36-1.59-1.11-1.61s-1.29.53-1.3,1.78V52.4h-1.4V44.59h1.4l0,2.85a2.21,2.21,0,0,1,1.61-.62A2.35,2.35,0,0,1,78,49.42Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #477c7c"
                  d="M18.84,52.39V46.88h1.21v.62a2.54,2.54,0,0,1,1.81-.71A2.06,2.06,0,0,1,24,49.14v3.25h-1.4v-3c0-.87-.46-1.26-1.12-1.26a1.25,1.25,0,0,0-1.27,1.41v2.89Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #477c7c"
                  d="M40.45,46.83h-.17a2.58,2.58,0,0,0-1.81.71v-.62H37.26v5.52h1.41V49.54a1.24,1.24,0,0,1,1.27-1.41,1.19,1.19,0,0,1,.51.1Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #83beb1"
                  d="M66.5,50.25H62.57c0,.64.65,1,1.49,1a2.07,2.07,0,0,0,1.38-.43l.72.8a3,3,0,0,1-5-2.16,2.7,2.7,0,0,1,5.39,0C66.53,49.63,66.51,50.12,66.5,50.25Zm-3.94-1.1h2.55a1.15,1.15,0,0,0-1.27-1.09A1.16,1.16,0,0,0,62.56,49.15Z"
                  transform="translate(0 -44.45)"
                /><path
                  style="fill: #477c7c"
                  d="M36.41,50.23H32.48c0,.65.65,1,1.49,1a2.07,2.07,0,0,0,1.38-.42l.72.79a2.71,2.71,0,0,1-2.14.84,2.68,2.68,0,0,1-2.88-3,2.7,2.7,0,0,1,5.39,0C36.44,49.62,36.42,50.1,36.41,50.23Zm-3.95-1.1H35a1.14,1.14,0,0,0-1.27-1.08A1.17,1.17,0,0,0,32.46,49.13Z"
                  transform="translate(0 -44.45)"
                /></svg
              >
            </td>
            <td style="padding-left: 30px;">
              <p
                style="font-size: 18px; font-weight: 300; color: #4c4d4e; margin: 5px 0 10px 0;"
              >
                {#if phone}
                  <span style="color:#83beb1;">Direct</span>
                  {phone} &nbsp;
                {/if}
                {#if mobile_phone}
                  <span style="color:#83beb1;">(m)</span>
                  {mobile_phone}
                {/if}
              </p>
              <p
                style="font-size: 18px; font-weight: 300; color: #4c4d4e; margin: 5px 0 10px 0;"
              >
                {email}
              </p>
              <p
                style="font-size: 18px; font-weight: 300; color: #4c4d4e; margin: 5px 0 10px 0;"
              >
                www.thunderbiotech.com
              </p>
            </td>
          </tr>
          <tr>
            <td colspan="2">
              <p
                style="font-size: 13px; color: #4c4d4e; margin: 5px 0; margin-top: 8px;"
              >
                Empowering Patients to Conquer Cancer&trade;
              </p>
            </td>
          </tr>
        </table>
      </div>
      <div style="margin-top: 1em;">
        <button on:click={selectText}>Select Result</button>
        <button on:click={copyHtml}>Copy HTML</button>
      </div>
    </div>
  </div>
</main>

<style>
  main {
    box-sizing: border-box;
    padding: 1em;
    width: 100vw;
    max-width: 100vw;
    margin: 0 auto;
    color: #4c4d4e;
    overflow-x: scroll;
  }

  @media (min-width: 768px) {
    .container {
      display: flex;
    }
  }

  h1 {
    color: #83beb1;
    font-size: 4em;
    font-weight: 100;
    margin-bottom: 1em;
  }

  @media (max-width: 767px) {
    h1 {
      font-size: 2em;
    }
  }

  h2 {
    font-weight: 700;
    font-size: 1.4em;
    margin-bottom: 1em;
  }

  form {
    padding: 1em;
    background: #f3f4f6;
    display: inline-block;
    width: 100%;
    max-width: 400px;
    border-radius: 8px;
  }

  @media (min-width: 768px) {
    form {
      margin-right: 2em;
    }
  }

  form input {
    width: 100%;
  }

  @media (min-width: 768px) {
    form input {
      width: auto;
    }
  }

  form > div {
    display: flex;
    justify-content: space-between;
  }

  @media (max-width: 767px) {
    form > div {
      display: block;
      justify-content: space-between;
    }
  }

  form > div > label {
    padding-right: 2em;
  }

  .result {
    padding: 2em 3em;
    border: 2px dashed #aaa;
    border-radius: 10px;
    overflow-x: scroll;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
