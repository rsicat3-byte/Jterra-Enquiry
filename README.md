<!doctype html>
<html lang="en-AU">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>JTerra Property Group | Enquiry Portal</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Young+Serif&family=Figtree:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
/* ------------------------------------------------------------------
   BRAND TOKENS. Swap these values to match the JTerra website exactly.
   ------------------------------------------------------------------ */
:root{
  --brand:#0f2747;        /* main brand colour (side panel, buttons) */
  --brand-ink:#f2f5fa;    /* text on brand colour */
  --accent:#b8893b;       /* accent (selected chips, highlights) */
  --accent-soft:#f3e9d6;
  --bg:#eef1f6;
  --surface:#ffffff;
  --ink:#121a26;
  --muted:#55637a;
  --line:#d3dae6;
  --danger:#a5321f;
  --ok:#1f6b4a;
  --display:"Young Serif", Georgia, "Times New Roman", serif;
  --body:"Figtree", system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --brand:#0b1d36; --brand-ink:#eef2f8; --accent:#d2a557; --accent-soft:#3a3019;
    --bg:#0c121c; --surface:#151e2c; --ink:#e8edf5; --muted:#9aa9bf; --line:#28344a;
    --danger:#f08a76; --ok:#7bd1a8;
  }
}
:root[data-theme="dark"]{
  --brand:#0b1d36; --brand-ink:#eef2f8; --accent:#d2a557; --accent-soft:#3a3019;
  --bg:#0c121c; --surface:#151e2c; --ink:#e8edf5; --muted:#9aa9bf; --line:#28344a;
  --danger:#f08a76; --ok:#7bd1a8;
}
*{box-sizing:border-box}
html,body{margin:0}
body{background:var(--bg);color:var(--ink);font-family:var(--body);font-size:16px;line-height:1.5;-webkit-font-smoothing:antialiased}
button,input,select,textarea{font:inherit;color:inherit}
a{color:inherit}
:focus-visible{outline:3px solid var(--accent);outline-offset:2px;border-radius:6px}

.shell{display:grid;grid-template-columns:minmax(300px,380px) 1fr;min-height:100vh}
.side{background:var(--brand);color:var(--brand-ink);padding:36px 34px;display:flex;flex-direction:column;gap:34px;position:sticky;top:0;height:100vh;overflow:auto}
.logo{display:flex;align-items:center;gap:12px;text-decoration:none}
.logo-mark{width:46px;height:46px;border-radius:10px;border:1.5px solid var(--accent);display:grid;place-items:center;font-family:var(--display);font-size:26px;color:var(--accent);flex:none}
.logo-mark.has-logo{border:0;border-radius:0}
.logo-mark img{width:100%;height:100%;object-fit:contain}
.logo-text b{display:block;font-weight:700;letter-spacing:.14em;font-size:18px;line-height:1.1}
.logo-text span{display:block;font-size:11px;letter-spacing:.3em;opacity:.8}
.side h1{font-family:var(--display);font-weight:400;font-size:clamp(30px,3vw,40px);line-height:1.12;margin:0 0 14px}
.side p{margin:0;opacity:.85;max-width:34ch}
.next{list-style:none;margin:0;padding:0;display:grid;gap:14px;counter-reset:n}
.next li{display:grid;grid-template-columns:30px 1fr;gap:12px;align-items:start;counter-increment:n;font-size:15px}
.next li::before{content:counter(n);width:30px;height:30px;border-radius:50%;border:1px solid rgba(255,255,255,.35);display:grid;place-items:center;font-size:13px;font-weight:600}
.side h2{font-size:14px;font-weight:600;margin:0 0 14px;opacity:.7}
.reach{margin-top:auto;display:grid;gap:6px;font-size:15px}
.reach a{text-decoration:none;border-bottom:1px solid rgba(255,255,255,.3);width:fit-content}
.tagline{font-family:var(--display);color:var(--accent);font-size:17px}

.main{padding:26px clamp(18px,4vw,56px) 120px;min-width:0}
.topbar{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-bottom:22px;flex-wrap:wrap}
.tabs{display:inline-flex;background:var(--surface);border:1px solid var(--line);border-radius:999px;padding:4px}
.tabs button{border:0;background:transparent;padding:8px 18px;border-radius:999px;cursor:pointer;font-weight:600;color:var(--muted)}
.tabs button[aria-selected="true"]{background:var(--brand);color:var(--brand-ink)}
.mode{font-size:13px;color:var(--muted)}
.notice{background:var(--accent-soft);border:1px solid var(--accent);border-radius:10px;padding:10px 14px;font-size:14px;margin-bottom:18px}

form{max-width:860px}
fieldset{border:0;border-top:1px solid var(--line);margin:0;padding:22px 0 8px}
fieldset:first-of-type{border-top:0;padding-top:0}
legend{font-family:var(--display);font-size:22px;padding:0;margin-bottom:4px;float:left;width:100%}
legend + *{clear:both}
.hint{color:var(--muted);font-size:14px;margin:0 0 16px}
.grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:16px}
.field{display:grid;gap:6px;margin-bottom:16px;min-width:0}
.field > label,.group-label{font-weight:600;font-size:14.5px}
.opt{font-weight:400;color:var(--muted);font-size:13px}
input[type=text],input[type=email],input[type=tel],select,textarea{width:100%;background:var(--surface);border:1px solid var(--line);border-radius:10px;padding:11px 13px;min-height:46px}
textarea{min-height:96px;resize:vertical}
input:focus,select:focus,textarea:focus{border-color:var(--brand);outline:3px solid color-mix(in srgb,var(--accent) 45%,transparent);outline-offset:0}
.chips{display:flex;flex-wrap:wrap;gap:8px}
.chip{position:relative}
.chip input{position:absolute;opacity:0;inset:0;width:100%;height:100%;margin:0;cursor:pointer}
.chip span{display:inline-block;padding:9px 15px;border-radius:999px;border:1px solid var(--line);background:var(--surface);font-size:14.5px;transition:background .12s,border-color .12s}
.chip input:checked + span{background:var(--brand);border-color:var(--brand);color:var(--brand-ink)}
.chip input:focus-visible + span{outline:3px solid var(--accent);outline-offset:2px}
.err{color:var(--danger);font-size:14px;min-height:0}
.err:empty{display:none}

.bar{position:fixed;left:0;right:0;bottom:0;background:color-mix(in srgb,var(--surface) 94%,transparent);backdrop-filter:blur(8px);border-top:1px solid var(--line);z-index:5}
.bar-in{margin-left:min(380px,33vw);padding:12px clamp(18px,4vw,56px);display:flex;gap:14px;align-items:center;justify-content:space-between;flex-wrap:wrap}
.bar small{color:var(--muted);font-size:13px;max-width:52ch}
.btn{border:0;border-radius:10px;padding:13px 24px;font-weight:700;cursor:pointer;background:var(--brand);color:var(--brand-ink)}
.btn:disabled{opacity:.6;cursor:progress}
.btn.ghost{background:transparent;color:var(--ink);border:1px solid var(--line);font-weight:600;padding:10px 16px}
.btn.small{padding:8px 12px;font-size:14px}

.done{max-width:680px;background:var(--surface);border:1px solid var(--line);border-radius:16px;padding:32px}
.done h2{font-family:var(--display);font-weight:400;font-size:30px;margin:0 0 8px}
.done dl{display:grid;grid-template-columns:150px 1fr;gap:8px 16px;margin:22px 0;font-size:15px}
.done dt{color:var(--muted)}
.done dd{margin:0;overflow-wrap:anywhere}

.staff-head{display:flex;gap:12px;align-items:center;flex-wrap:wrap;margin-bottom:16px}
.staff-head h2{font-family:var(--display);font-weight:400;font-size:28px;margin:0;flex:1 1 auto}
.staff-head input{max-width:260px}
.stats{display:flex;gap:22px;flex-wrap:wrap;color:var(--muted);font-size:14px;margin-bottom:16px}
.stats b{color:var(--ink);font-size:20px;font-family:var(--display);font-weight:400;margin-right:6px}
.list{display:grid;gap:8px}
details.row{background:var(--surface);border:1px solid var(--line);border-radius:12px}
details.row summary{list-style:none;cursor:pointer;padding:14px 16px;display:grid;grid-template-columns:minmax(140px,1.2fr) 2fr minmax(110px,.9fr) 110px;gap:12px;align-items:center;font-size:14.5px}
details.row summary::-webkit-details-marker{display:none}
details.row summary b{font-size:15.5px}
details.row summary .m{color:var(--muted)}
details.row[open]{border-color:var(--brand)}
.row-body{border-top:1px solid var(--line);padding:16px;display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:12px 22px;font-size:14.5px}
.row-body div span{display:block;color:var(--muted);font-size:13px}
.row-body .wide{grid-column:1/-1;white-space:pre-wrap;overflow-wrap:anywhere}
.row-actions{grid-column:1/-1;display:flex;justify-content:flex-end}
.empty{border:1px dashed var(--line);border-radius:12px;padding:34px;text-align:center;color:var(--muted)}
.copybox{width:100%;min-height:180px;margin-top:14px;font-family:ui-monospace,Menlo,Consolas,monospace;font-size:12.5px}
[hidden]{display:none !important}

@media (max-width:860px){
  .shell{grid-template-columns:1fr}
  .side{position:static;height:auto;padding:26px 22px;gap:22px}
  .next,.side h2{display:none}
  .reach{margin-top:0}
  .bar-in{margin-left:0}
  .grid{grid-template-columns:1fr}
  details.row summary{grid-template-columns:1fr 1fr}
  .done dl{grid-template-columns:1fr;gap:2px}
  .done dd{margin-bottom:10px}
}
@media (prefers-reduced-motion:reduce){*{transition:none !important}}
</style>
</head>
<body>
<div class="shell">

  <aside class="side">
    <a class="logo" href="https://jterrapropertygroup.com.au/" target="_blank" rel="noopener">
      <!-- LOGO: add a file named logo.svg (or change src to logo.png) to the repo root -->
      <span class="logo-mark" id="logoMark" aria-hidden="true"><img src="logo.svg" alt="" onload="this.parentNode.classList.add('has-logo')" onerror="this.parentNode.textContent='J'"></span>
      <span class="logo-text"><b>JTERRA</b><span>PROPERTY GROUP</span></span>
    </a>

    <div>
      <h1>Tell us what you're looking for.</h1>
      <p>It takes about two minutes. Fill in what you know and skip the rest. There is no obligation.</p>
    </div>

    <div>
      <h2>What happens next</h2>
      <ol class="next">
        <li>Your enquiry goes straight to the JTerra team.</li>
        <li>A property specialist contacts you the way you prefer.</li>
        <li>We shortlist land, packages or homes that fit your brief.</li>
      </ol>
    </div>

    <div class="reach">
      <span class="tagline">Your Property. Our Priority.</span>
      <a href="tel:+61481042723">+61 481 042 723</a>
      <a href="tel:+61433422817">+61 433 422 817</a>
      <a href="mailto:jeanille@jterrapropertygroup.com.au">jeanille@jterrapropertygroup.com.au</a>
    </div>
  </aside>

  <main class="main">
    <div class="notice" id="setupNotice" hidden>Setup needed: no endpoint is configured, so enquiries are not being delivered. See README.md, step 3.</div>

    <!-- ===================== ENQUIRY FORM ===================== -->
    <section id="viewForm">
      <form id="form" novalidate>
        <div style="position:absolute;left:-9999px" aria-hidden="true"><label>Leave this empty<input type="text" name="website" id="website" tabindex="-1" autocomplete="off"></label></div>
        <fieldset>
          <legend>About you</legend>
          <p class="hint">Give us a phone number or an email so we can reply. Everything else on this page is optional.</p>
          <div class="grid">
            <div class="field"><label for="firstName">First name</label><input id="firstName" name="firstName" type="text" autocomplete="given-name"></div>
            <div class="field"><label for="lastName">Last name</label><input id="lastName" name="lastName" type="text" autocomplete="family-name"></div>
            <div class="field"><label for="email">Email</label><input id="email" name="email" type="email" autocomplete="email" inputmode="email"></div>
            <div class="field"><label for="phone">Phone</label><input id="phone" name="phone" type="tel" autocomplete="tel" inputmode="tel" placeholder="04xx xxx xxx"></div>
          </div>
          <div class="err" id="contactErr" role="alert"></div>
          <div class="field">
            <span class="group-label" id="lblContact">Best way to reach you</span>
            <div class="chips" data-single="contactMethod" role="group" aria-labelledby="lblContact"></div>
          </div>
        </fieldset>

        <fieldset>
          <legend>What you're after</legend>
          <div class="field" style="margin-top:6px">
            <span class="group-label" id="lblService">I'm interested in <span class="opt">choose any</span></span>
            <div class="chips" data-multi="services" role="group" aria-labelledby="lblService"></div>
          </div>
          <div class="field">
            <span class="group-label" id="lblBuyer">Which best describes you</span>
            <div class="chips" data-single="buyerType" role="group" aria-labelledby="lblBuyer"></div>
          </div>
        </fieldset>

        <fieldset>
          <legend>Your search</legend>
          <div class="grid" style="margin-top:6px">
            <div class="field"><label for="suburb1">Preferred suburb, first choice</label><input id="suburb1" name="suburb1" type="text" list="suburbs" placeholder="e.g. Clyde North"></div>
            <div class="field"><label for="suburb2">Preferred suburb, second choice</label><input id="suburb2" name="suburb2" type="text" list="suburbs" placeholder="e.g. Officer"></div>
          </div>
          <datalist id="suburbs">
            <option value="Clyde North"><option value="Officer"><option value="Cranbourne"><option value="Narre Warren South"><option value="Berwick"><option value="Endeavour Hills">
          </datalist>
          <div class="field">
            <span class="group-label" id="lblBudget">Budget</span>
            <div class="chips" data-single="budget" role="group" aria-labelledby="lblBudget"></div>
          </div>
          <div class="field">
            <span class="group-label" id="lblPre">Finance pre-approval</span>
            <div class="chips" data-single="preApproval" role="group" aria-labelledby="lblPre"></div>
          </div>
          <div class="field">
            <span class="group-label" id="lblTime">When are you looking to buy</span>
            <div class="chips" data-single="timeframe" role="group" aria-labelledby="lblTime"></div>
          </div>
        </fieldset>

        <fieldset>
          <legend>Anything else</legend>
          <div class="field" style="margin-top:6px"><label for="message">Message</label><textarea id="message" name="message" placeholder="Land size, number of bedrooms, questions for the team"></textarea></div>
          <div class="grid">
            <div class="field"><label for="source">How did you hear about us</label>
              <select id="source" name="source">
                <option value="">Select</option><option>Referral from a friend or family</option><option>Facebook or Instagram</option><option>Google search</option><option>Event or open day</option><option>Other</option>
              </select>
            </div>
            <div class="field" style="align-content:end">
              <label class="chip" style="width:fit-content"><input type="checkbox" id="updates" name="updates"><span>Send me market updates and new listings</span></label>
            </div>
          </div>
        </fieldset>

        <div class="bar">
          <div class="bar-in">
            <small>By sending this enquiry you agree to JTerra contacting you about it. See the <a href="https://jterrapropertygroup.com.au/privacy-policy" target="_blank" rel="noopener">privacy policy</a>.</small>
            <div style="display:flex;gap:10px;align-items:center">
              <span class="err" id="sendErr" role="alert"></span>
              <button class="btn" type="submit" id="sendBtn">Send enquiry</button>
            </div>
          </div>
        </div>
      </form>

      <div class="done" id="done" hidden tabindex="-1">
        <h2>Enquiry sent</h2>
        <p id="doneMsg" style="margin:0;color:var(--muted)"></p>
        <dl id="doneList"></dl>
        <button class="btn ghost" type="button" id="againBtn">Send another enquiry</button>
      </div>
    </section>

  </main>
</div>

<script>
(function(){
"use strict";

/* ==================================================================
   CONFIG: paste the Google Apps Script web app URL between the quotes.
   It looks like https://script.google.com/macros/s/XXXX/exec
   ================================================================== */
var ENDPOINT = "https://script.google.com/macros/s/AKfycbzQU2zh8oPe_mtGNE11-LWas6OWWsNrawPn23Ta0JOknBuKcpnjG-tjSk14czoedwwUXg/exec";

var OPTIONS = {
  contactMethod:["Phone call","Email","SMS or WhatsApp"],
  services:["First home buyer agency","House and land packages","Property investment","Property management","Referral program","General enquiry"],
  buyerType:["First home buyer","Upgrading or next home","Investor","Landlord","Not sure yet"],
  budget:["Under $500k","$500k to $650k","$650k to $800k","$800k to $1m","Over $1m","Not sure yet"],
  preApproval:["Yes, pre-approved","In progress","Not yet","Need help finding a broker"],
  timeframe:["Ready now","1 to 3 months","3 to 6 months","6 to 12 months","Just researching"]
};
var LABELS = [
  ["firstName","First name"],["lastName","Last name"],["email","Email"],["phone","Phone"],
  ["contactMethod","Preferred contact"],["services","Interested in"],["buyerType","Buyer type"],
  ["suburb1","Suburb 1"],["suburb2","Suburb 2"],["budget","Budget"],["preApproval","Pre-approval"],
  ["timeframe","Timeframe"],["message","Message"],["source","Heard via"]
];
var $ = function(id){return document.getElementById(id);};
if (!ENDPOINT) $("setupNotice").hidden = false;

document.querySelectorAll(".chips").forEach(function(box){
  var name = box.dataset.single || box.dataset.multi;
  OPTIONS[name].forEach(function(opt){
    var l = document.createElement("label"); l.className = "chip";
    var i = document.createElement("input"); i.type = "checkbox"; i.name = name; i.value = opt;
    var s = document.createElement("span"); s.textContent = opt;
    l.appendChild(i); l.appendChild(s); box.appendChild(l);
    if (box.dataset.single) i.addEventListener("change", function(){
      if (i.checked) box.querySelectorAll("input").forEach(function(o){ if (o !== i) o.checked = false; });
    });
  });
});

function val(id){ return ($(id).value || "").trim(); }
function picked(name){ return Array.prototype.slice.call(document.querySelectorAll('input[name="'+name+'"]:checked')).map(function(i){return i.value;}); }
function newId(){ return "JT-" + Date.now().toString(36).toUpperCase() + "-" + Math.random().toString(36).slice(2,6).toUpperCase(); }
function show(v){ return Array.isArray(v) ? v.join(", ") : (v || ""); }

function collect(){
  return {
    id:newId(), submittedAt:new Date().toISOString(),
    firstName:val("firstName"), lastName:val("lastName"), email:val("email"), phone:val("phone"),
    contactMethod:picked("contactMethod")[0] || "", services:picked("services").join(", "), buyerType:picked("buyerType")[0] || "",
    suburb1:val("suburb1"), suburb2:val("suburb2"), budget:picked("budget")[0] || "",
    preApproval:picked("preApproval")[0] || "", timeframe:picked("timeframe")[0] || "",
    message:val("message"), source:val("source"), updates:$("updates").checked ? "Yes" : "No",
    page:location.href, website:val("website")
  };
}

$("form").addEventListener("submit", async function(ev){
  ev.preventDefault();
  $("contactErr").textContent = ""; $("sendErr").textContent = "";
  var e = collect();
  if (!e.email && !e.phone){ $("contactErr").textContent = "Add a phone number or an email so the team can reply."; $("email").focus(); return; }
  if (e.email && !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(e.email)){ $("contactErr").textContent = "That email address doesn't look right. Check it and send again."; $("email").focus(); return; }
  if (!ENDPOINT){ $("sendErr").textContent = "This form is not connected yet. Call +61 481 042 723."; return; }
  var btn = $("sendBtn"); btn.disabled = true; btn.textContent = "Sending\u2026";
  try {
    /* text/plain keeps this a simple request, so the browser sends no CORS preflight (Apps Script cannot answer one) */
    var res = await fetch(ENDPOINT, {method:"POST", headers:{"Content-Type":"text/plain;charset=utf-8"}, body:JSON.stringify(e), redirect:"follow"});
    var out = await res.json();
    if (!out || out.ok !== true) throw new Error("rejected");
    confirmSent(e);
  } catch(err){
    $("sendErr").textContent = "This enquiry was not sent. Try again, or call +61 481 042 723.";
  } finally {
    btn.disabled = false; btn.textContent = "Send enquiry";
  }
});

function confirmSent(e){
  $("form").hidden = true; $("done").hidden = false;
  $("doneMsg").textContent = (e.firstName ? "Thanks, " + e.firstName + ". " : "Thank you. ") + "The JTerra team has your enquiry. Reference " + e.id + ".";
  var dl = $("doneList"); dl.textContent = "";
  LABELS.forEach(function(p){
    var v = show(e[p[0]]); if (!v) return;
    var dt = document.createElement("dt"); dt.textContent = p[1];
    var dd = document.createElement("dd"); dd.textContent = v;
    dl.appendChild(dt); dl.appendChild(dd);
  });
  $("done").focus(); window.scrollTo({top:0});
}
$("againBtn").addEventListener("click", function(){
  $("form").reset(); $("done").hidden = true; $("form").hidden = false; $("firstName").focus();
});
})();
</script>
</body>
</html>
