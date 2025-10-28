<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>FastBooking — Hotels, Flights, Cars & Trains</title>
  <meta name="description" content="FastBooking — search hotels, flights, cars and trains. Best deals for UK, USA, Canada, Schengen, Kuwait and more." />
  <style>
    body{font-family:Inter, system-ui, Arial, sans-serif;margin:0;background:#f4f7fb;color:#111}
    header{background:#0f7cda;color:white;padding:28px 16px;text-align:center}
    .container{max-width:1000px;margin:26px auto;padding:0 16px}
    .card{background:white;margin-bottom:18px;padding:18px;border-radius:10px;box-shadow:0 6px 20px rgba(12,40,80,0.06)}
    .grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
    input,select,textarea{padding:10px;border-radius:8px;border:1px solid #ddd;width:100%;box-sizing:border-box}
    button{background:#0f7cda;color:white;border:none;padding:10px 14px;border-radius:8px;cursor:pointer}
    footer{text-align:center;font-size:13px;padding:18px;color:#666}
    a{color:#0f7cda;text-decoration:none}
    @media(max-width:720px){.grid{grid-template-columns:1fr}}
  </style>
</head>
<body>
  <header>
    <h1 style="margin:0;font-size:28px">FastBooking</h1>
    <p style="margin:6px 0 0 0;opacity:.95">Hotels • Flights • Car Rentals • Trains — best partner deals worldwide</p>
  </header>

  <main class="container">
    <section class="card">
      <h2 style="margin-top:0">Quick hotel search</h2>
      <div class="grid">
        <div>
          <label>Destination</label>
          <input id="hotel-dest" placeholder="e.g. London, UK" />
        </div>
        <div>
          <label>Dates (optional)</label>
          <input id="hotel-dates" placeholder="YYYY-MM-DD to YYYY-MM-DD" />
        </div>
      </div>
      <div style="margin-top:12px">
        <button onclick="searchBooking()">Search hotels on Booking.com</button>
      </div>
    </section>

    <section class="card">
      <h2 style="margin-top:0">Quick flight search</h2>
      <div class="grid">
        <div><label>From</label><input id="from" placeholder="e.g. LHR" /></div>
        <div><label>To</label><input id="to" placeholder="e.g. JFK" /></div>
      </div>
      <div style="margin-top:12px">
        <button onclick="openSkyscanner()">Search flights on Skyscanner</button>
      </div>
    </section>

    <section class="card">
      <h2 style="margin-top:0">Cars & Trains</h2>
      <p>Use trusted partners for rentals and rail tickets.</p>
      <div style="display:flex;gap:12px;flex-wrap:wrap">
        <a href="https://www.rentalcars.com/?affiliate_id=YOUR_AFFILIATE_ID" target="_blank" rel="noopener">Car rentals (Rentalcars)</a>
        <a href="https://www.trip.com/?aff=YOUR_AFFILIATE_ID" target="_blank" rel="noopener">Trains & more (Trip.com)</a>
      </div>
    </section>

    <section class="card">
      <h3 style="margin-top:0">About FastBooking</h3>
      <p>FastBooking compares top partner offers and links you to them via affiliate partners. Booking via our links helps keep this site free — we may earn a commission at no extra cost to you.</p>
    </section>

    <section class="card">
      <h3 style="margin-top:0">Contact</h3>
      <form onsubmit="event.preventDefault(); alert('Thanks! We will contact you.');">
        <input placeholder="Your name" required><br><br>
        <input type="email" placeholder="Email" required><br><br>
        <textarea placeholder="Message" style="width:100%;height:96px;border-radius:8px;border:1px solid #ddd"></textarea><br><br>
        <button type="submit">Send message</button>
      </form>
    </section>
  </main>

  <footer>
    <div>Affiliate disclosure: FastBooking may earn commissions from partner bookings.</div>
    <div style="margin-top:6px"><a href="/privacy.html">Privacy & cookies</a> • <a href="/terms.html">Terms</a></div>
  </footer>

  <script>
    function searchBooking(){
      const dest = encodeURIComponent(document.getElementById('hotel-dest').value || 'London');
      // Booking deeplink — replace YOUR_AFFILIATE_ID with your Booking.com partner id (aid)
      const url = `https://www.booking.com/searchresults.html?ss=${dest}&aid=YOUR_AFFILIATE_ID`;
      window.open(url,'_blank');
    }
    function openSkyscanner(){
      const from = encodeURIComponent(document.getElementById('from').value || 'LHR');
      const to = encodeURIComponent(document.getElementById('to').value || 'JFK');
      // Skyscanner example deeplink — replace YOUR_AFFILIATE_ID with your Skyscanner partner id
      const url = `https://www.skyscanner.net/transport/flights/${from}/${to}/?affid=YOUR_AFFILIATE_ID`;
      window.open(url,'_blank');
    }
  </script>
</body>
</html>
