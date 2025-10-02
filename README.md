# fin<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>JKS Group App Updated Full</title>
<style>
  body {background: #20242b; color: #fff; font-family: 'Segoe UI', Arial, sans-serif; margin: 0; padding: 0;}
  header, nav {display: flex; justify-content: center; gap: 20px; background: #141b29; padding: 18px 0; position: sticky; top: 0; z-index: 999;}
  header {font-weight: 700; font-size: 1.6em; color: #00e1ff; text-shadow: 0 0 14px #0fccfcc5;}
  nav button {background:none; border:2.5px solid #0fccfc; border-radius:9px; color:#0fccfc; font-weight:700; cursor:pointer; padding:12px 22px; user-select:none; transition:0.3s;}
  nav button:hover, .nav-active {background:#0fccfc; color:#202733;}
  main {max-width: 1100px; margin: 38px auto 60px; padding: 0 14px;}
  .main-title {text-align: center; font-size: 2.3em; color: #00e1ff; margin-bottom: 37px; font-weight: 700; letter-spacing: 2px; text-shadow: 0 0 14px #0fccfcc5;}
  .dashboard {display: grid; grid-template-columns: repeat(auto-fit,minmax(250px, 1fr)); gap: 34px 46px; justify-content: center; align-items:center; max-width: 980px; margin: 0 auto;}
  .folder-card {background: #23273b; border: 3px solid #ffe27f; border-radius: 12px; min-height: 135px; font-weight: 700; font-size: 1.25em; color: #ffe27f; text-align: center; cursor: pointer; box-shadow: 0 0 20px 4px #fff68d85, 0 6px 26px #101722b3; padding: 42px 16px; user-select:none; transition:0.4s;}
  .folder-card:hover {background-color:#ffe27f; color:#171e29; border-color:#0fccfc; box-shadow:0 0 28px 9px #0fccfcbb, 0 6px 36px #2565a05f; transform: scale(1.07);}
  .section-title {color:#ffe27f; font-size:1.6em; font-weight: 700; margin: 24px auto 26px auto; letter-spacing: 1.3px; text-shadow: 0 0 16px #ffe27fc0; text-align: center;}
  .service-list, .category-list {display: grid; gap: 28px; grid-template-columns: repeat(auto-fit,minmax(200px,1fr)); justify-content: center; margin-bottom: 30px; margin-top: 18px;}
  .service-card, .category-card {background: #23273a; border: 2.5px solid #ffe27f; border-radius: 12px; min-height: 80px; color: #ffe27f; font-weight: 700; font-size: 1.1em; cursor: pointer; text-align:center; box-shadow: 0 0 18px 5px #ffeb8499, 0 6px 18px #1e2635a4; padding: 26px 10px; transition: 0.25s;}
  .service-card:hover, .category-card:hover {background-color: #ffe27f; color: #242d3a; border-color: #0fccfc; box-shadow: 0 0 28px 9px #0fccfc77, 0 9px 38px #18408bab;transform: scale(1.07);}
  .back-btn {background:#ffe27f; color:#252a39; font-weight: 800; border: 2.5px solid #ffe27f; border-radius: 15px; padding: 15px 60px; font-size: 1.18em; box-shadow: 2px 2px 22px #ffe27fca; margin: 38px auto 28px; display: block; width: max-content; cursor: pointer; transition: 0.28s; user-select:none;}
  .back-btn:hover {background-color: #0fccfc; color: #fff; border-color: #0fccfc; box-shadow: 0 0 30px 8px #0fccfcbb;}
  form.contact-form { max-width: 480px; margin: 20px auto 50px auto; padding: 25px 26px; background: #172440; border-radius: 14px; border: 2px solid #0fccfccc; color: #90c8ff; font-size: 1.1em; text-align: left; }
  form.contact-form label { font-weight: 700; margin-bottom: 10px; display: block; color: #aad4fc; }
  form.contact-form input, form.contact-form textarea, form.contact-form select { background: #11253b; border: 1.5px solid #0fccfab8; padding: 13px 17px; border-radius: 8px; color: #cddcff; font-size: 16px; margin-bottom: 24px; box-sizing: border-box; width: 100%; resize: vertical; }
  form.contact-form input:focus, form.contact-form textarea:focus, form.contact-form select:focus { outline: none; border-color: #00b6f1; background: #293767; }
  form.contact-form button { width: 100%; color: #193140; background: #00e1ff; font-weight: 900; font-size: 1.18em; border: none; border-radius: 12px; padding: 14px 0; cursor: pointer; transition: background-color 0.2s ease; }
  form.contact-form button:hover { background-color: #38edff; }
  /* E-commerce Images */
  .ecom-imgs {display: grid; grid-template-columns: repeat(auto-fit,minmax(120px,1fr)); gap: 12px; margin-bottom: 15px;}
  .ecom-imgs img {width: 100%; height: 80px; border-radius: 8px; object-fit: cover; }
  #map { max-width: 600px; height: 420px; margin: 20px auto; border-radius: 12px; border: 2px solid #0fccfc;}
  video#video {max-width: 100%; height: auto; border-radius: 12px; border: 2px solid #0fccfc; margin-top: 20px;}
</style>
</head>
<body>

<header>JKS Group of Business</header>

<nav>
  <button onclick="showPage('dashboard')" class="nav-active">Dashboard</button>
  <button onclick="showPage('profile')">Profile</button>
  <button onclick="showPage('wallet')">Wallet</button>
  <button onclick="showPage('orders')">Orders</button>
  <button onclick="showPage('camera')">Camera</button>
  <button onclick="showPage('maps')">Google Maps</button>
</nav>

<main>
  <section id="dashboard" class="dashboard"></section>
  
  <!-- Other Pages -->
  <section id="profile" style="display:none; max-width:500px; margin: 30px auto;">
    <h2 class="section-title">Profile</h2>
    <form class="contact-form">
      <label>Full Name:</label> <input type="text" id="profileName" />
      <label>Email:</label> <input type="email" id="profileEmail" />
      <label>Mobile Number:</label> <input type="tel" id="profilePhone" />
      <label>Address:</label> <textarea id="profileAddress" rows="3"></textarea>
      <button type="button" onclick="alert('Profile updated!')">Update Profile</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="wallet" style="display:none; max-width: 500px; margin: 30px auto;">
    <h2 class="section-title">Wallet</h2>
    <p>Your current balance: ₹<span id="walletBalance">10000</span></p>
    <form class="contact-form" onsubmit="addMoney(event)">
      <label>Add Money:</label>
      <input type="number" id="addMoneyInput" min="1" placeholder="Enter amount to add" required />
      <button type="submit">Add Funds</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="orders" style="display:none; max-width: 700px; margin: 30px auto;">
    <h2 class="section-title">Orders</h2>
    <table style="width: 100%; border-collapse: collapse; font-size: 1em; background: #1c2236; border-radius: 8px; overflow: hidden;">
      <thead>
        <tr>
          <th style="padding: 12px; border-bottom: 2px solid #00e1ff;">Order ID</th>
          <th style="padding: 12px; border-bottom: 2px solid #00e1ff;">Product/Service</th>
          <th style="padding: 12px; border-bottom: 2px solid #00e1ff;">Status</th>
        </tr>
      </thead>
      <tbody id="orderListBody">
        <tr><td>1001</td><td>Pizza</td><td style="color:#00ffc0;">Delivered</td></tr>
        <tr><td>1002</td><td>Car Wash</td><td style="color:#ffe27f;">Pending</td></tr>
        <tr><td>1003</td><td>Loan Enquiry</td><td style="color:#00c2ff;">In Progress</td></tr>
      </tbody>
    </table>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="serviceView" style="display:none; flex-direction: column; align-items: center;">
    <div class="section-title" id="serviceTitle"></div>
    <div class="service-list" id="serviceList"></div>
    <form id="contactForm" class="contact-form" style="display:none;">
      <h3 id="contactTitle"></h3>
      <label>Name:</label><input type="text" id="userName" required/>
      <label>Mobile Number:</label><input type="tel" id="userPhone" maxlength="10" pattern="[6-9][0-9]{9}" required/>
      <label>Message:</label><textarea id="userMessage" rows="4" required></textarea>
      <button type="button" onclick="submitContactForm()">Submit via WhatsApp</button>
      <button type="button" class="back-btn" onclick="backToServiceList()">Back to Services</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="eventsView" style="display:none; flex-direction: column; align-items: center;">
    <div class="section-title" id="eventsCategoryTitle"></div>
    <div class="category-list" id="eventsCategories"></div>
    <div class="service-list" id="eventsServiceList"></div>
    <form id="eventContactForm" class="contact-form" style="display:none;">
      <h3 id="eventsContactTitle"></h3>
      <label>Name:</label><input id="eventsUserName" type="text" required />
      <label>Mobile Number:</label><input id="eventsUserPhone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required />
      <label>Budget:</label>
      <select id="eventsBudget" >
        <option value="">Select Budget (only for Customized)</option>
        <option value="10k to 50k">10k to 50k</option>
        <option value="50k to 1L">50k to 1L</option>
        <option value="1L to 5L">1L to 5L</option>
        <option value="5L to 10L">5L to 10L</option>
        <option value="Above 10L">Above 10L</option>
      </select>
      <label>Capacity:</label>
      <select id="eventsCapacity" >
        <option value="">Select Capacity (only for Customized)</option>
        <option value="5-30 people">5-30 people</option>
        <option value="30-60 people">30-60 people</option>
        <option value="60-90 people">60-90 people</option>
        <option value="90-130 people">90-130 people</option>
        <option value="Above 130 people">Above 130 people</option>
      </select>
      <label>Message:</label><textarea id="eventsUserMessage" rows="4" required></textarea>
      <button type="button" onclick="submitEventsForm()">Submit via WhatsApp</button>
      <button type="button" class="back-btn" onclick="backToEventsCategory()">Back to Category</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="ecomView" style="display:none; flex-direction: column; align-items: center;">
    <div class="section-title">My E-commerce</div>
    <div class="category-list" id="ecomCategories"></div>
    <div id="ecomCategoryContent"></div>
    <div class="service-list" id="ecomServiceList"></div>
    <form id="ecomOrderForm" class="contact-form" style="display:none;">
      <h3 id="ecomOrderTitle"></h3>
      <label>Name:</label><input name="name" type="text" required />
      <label>Mobile Number:</label><input name="phone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required />
      <label>Order Details:</label><textarea name="orderDetails" rows="3" required></textarea>
      <label>Delivery Address:</label><textarea name="address" required></textarea>
      <button type="submit">Submit Order</button>
      <button type="button" class="back-btn" onclick="backToEcomServices()">Back to Services</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="camera" style="display:none; text-align:center;">
    <h2 class="section-title">Camera</h2>
    <video id="video" autoplay muted playsinline></video>
    <div style="margin-top: 25px;">
      <button onclick="switchCamera()">Switch Camera</button>
      <button onclick="capturePhoto()">Capture Photo</button>
    </div>
    <canvas id="canvas" style="display:none;"></canvas>
    <div id="photoOutput" style="margin-top: 20px;"></div>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="maps" style="display:none; text-align:center;">
    <h2 class="section-title">Google Maps</h2>
    <div id="map"></div>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

</main>
<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEY"></script>
<script>
  const folders = [
    {id:'ecommerce',label:'My E-commerce'},
    {id:'events',label:'Events & Catering'},
    {id:'courier',label:'Courier & Ride Booking'},
    {id:'job',label:'Job Consultancy & Services'},
    {id:'tours',label:'Tours & Travels'},
    {id:'realestate',label:'Real Estate & Construction'},
    {id:'investment',label:'Investment & Business'},
    {id:'loans',label:'Loans & Insurance'},
    {id:'home',label:'Home Services'}
  ];
  const moduleServices = {
    courier:['Courier Booking','Ride Booking','Tracking','Support','Rental Vehicles'],
    job:['Job Search','Post Resume','Local Jobs','Non-Local Jobs','PG & Hostel','Services Marketplace'],
    tours:['Tour Bookings','Custom & Regular Tours','Stay Booking','Vehicle Booking','Train/Bus/Flight Tickets'],
    realestate:['Buy','Sell','Rent','Key Services','Construction','Industry'],
    investment:['Gold','Silver','Real Estate','Business Opportunity','Mutual Funds'],
    loans:['Loan Enquiry','Car Insurance','Bike Insurance','Housing Loans','Personal Loans','Health Insurance'],
    home:['CC Camera Installation','Computer Repair','Car Wash','Mobile Repair','Chef Services','Bouncers','Bike Mechanic','Car Mechanic','Electrician','Painter','Plumber','Driver']
  };
  const ecom = {
    Groceries:['Milk','Meat','Fruits','Vegetables','Flowers','Others'],
    Food:['Biriyani','Tiffins','Ice Cream','Pizza','Burgers','Rolls'],
    Pharmacy:['Medicines','Health Products','Supplements','Care Products']
  };
  const ecomImgs = {
    Groceries: ['groceries','fruits','vegetables','milk','meat','flowers','tomato','carrot','banana','snacks'],
    Food:['pizza','biriyani','ice-cream','tiffin','burger','rolls','dosa','biryani','pasta','fruit'],
    Pharmacy:['pharmacy','medicine','tablet','capsule','syrup','care','first-aid','bandage','mask','prescription']
  };
  const eventsCategories = {
    package: [
      {name:"Silver (50k -160k)",services:["Decoration","Catering","DJ & Music","Guest House","Chocolate & Cake","Games & Entertainment"]},
      {name:"Gold (150k - 300k)",services:["Decoration","Catering","Photography","Anchor & Actors","Vehicles"]},
      {name:"Diamond (500k - 5M)",services:["Premium Decoration","Luxury Catering","Video & Photography","Celebrity Anchors"]},
      {name:"Platinum (500k - 800k)",services:["Special Decoration","Exclusive Catering","Top DJs","Private Guest House"]}
    ],
    customized:["Decoration","Catering","Photography & Videography","Anchor & Actors","DJ & Singers","Guest House","Chocolate & Cake","Games & Entertainment","Jewellery","Invitation Cards","Vehicles","Return Gifts","Makeup Artist","Mehandi Artist","Clothing & Accessories"],
    premium:["Decoration","Catering","Photography & Videography","Anchor & Actors","DJ & Singers","Guest House","Chocolate & Cake","Games & Entertainment","Jewellery","Invitation Cards","Vehicles","Return Gifts","Makeup Artist","Mehandi Artist","Clothing & Accessories"]
  };
  let currentModule = '',currentService = '',currentEventCategory = '',currentEventService = '',currentEcomCategory = '';
  let walletBalance = 10000;

  function showPage(page){
    document.querySelectorAll('main > section').forEach(s => s.style.display = 'none');
    document.getElementById(page).style.display = 'block';
    if(page=='dashboard'){renderDashboard();}
    else if(page=='camera'){startCamera();}
    else if(page=='maps'){if(!window.mapLoaded){initMap();window.mapLoaded=true;}}
  }
  function renderDashboard(){
    const dash = document.getElementById('dashboard');
    dash.innerHTML = '';
    folders.forEach(f => {
      let d = document.createElement('div');
      d.className = 'folder-card';
      d.textContent = f.label;
      d.onclick = () => openModule(f.id);
      dash.appendChild(d);
    });
  }
  function openModule(mod){
    currentModule = mod;
    currentService = '';
    if(mod=='events'){openEventsDashboard();return;}
    if(mod=='ecommerce'){openEcomDashboard();return;}
    const listEl = document.getElementById('serviceList');
    listEl.innerHTML = '';
    moduleServices[mod].forEach(s => {
      let d = document.createElement('div');
      d.className = 'service-card';
      d.textContent = s;
      d.onclick = () => openContactForm(s);
      listEl.appendChild(d);
    });
    document.getElementById('serviceTitle').textContent = folders.find(f=>f.id==mod).label;
    showPage('serviceView');
  }
  function openContactForm(service){
    currentService = service;
    document.getElementById('serviceList').style.display = 'none';
    const form = document.getElementById('contactForm');
    form.style.display = 'block';
    document.getElementById('contactTitle').textContent = 'Contact for ' + service;
    clearInputs(['userName','userPhone','userMessage']);
  }
  function backToServiceList(){
    document.getElementById('contactForm').style.display = 'none';
    document.getElementById('serviceList').style.display = 'grid';
  }
  function submitContactForm(){
    const name = document.getElementById('userName').value.trim();
    const phone = document.getElementById('userPhone').value.trim();
    const message = document.getElementById('userMessage').value.trim();
    if(!name||!phone||!message){
      alert('Please fill all details');
      return;
    }
    const wnumber = '8977143043';
    const fullMsg = `Name: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0AMessage: ${encodeURIComponent(message)}%0AService: ${encodeURIComponent(currentService)}`;
    window.open(`https://wa.me/${wnumber}?text=${fullMsg}`, '_blank');
  }

  // Events & Catering
  function openEventsDashboard() {
    currentEventCategory = '';
    currentEventService = '';
    document.getElementById('dashboard').style.display = 'none';
    document.getElementById('serviceView').style.display = 'none';
    document.getElementById('ecomView').style.display = 'none';
    document.getElementById('eventsView').style.display = 'block';
    const catsDiv = document.getElementById('eventsCategories');
    catsDiv.innerHTML = '';
    for (const cat in eventsCategories) {
      const d = document.createElement('div');
      d.className = 'category-card';
      d.textContent = cat.charAt(0).toUpperCase() + cat.slice(1);
      d.onclick = () => openEventsCategory(cat);
      catsDiv.appendChild(d);
    }
    document.getElementById('eventsServiceList').innerHTML = '';
    document.getElementById('eventContactForm').style.display = 'none';
    document.getElementById('eventsCategoryTitle').textContent = 'Events & Catering Categories';
  }
  function openEventsCategory(cat) {
    currentEventCategory = cat;
    currentEventService = '';
    document.getElementById('eventContactForm').style.display = 'none';
    document.getElementById('eventsServiceList').style.display = 'flex';
    const srvList = document.getElementById('eventsServiceList');
    srvList.innerHTML = '';
    document.getElementById('eventsCategoryTitle').textContent = cat.charAt(0).toUpperCase() + cat.slice(1) + ' Services';
    if (cat === 'package') {
      eventsCategories.package.forEach(pkg => {
        const d = document.createElement('div');
        d.className = 'service-card';
        d.style.width = '280px';
        d.textContent = pkg.name;
        d.onclick = () => openPackageServices(pkg.name, pkg.services);
        srvList.appendChild(d);
      });
    } else {
      eventsCategories[cat].forEach(svc => {
        const d = document.createElement('div');
        d.className = 'service-card';
        d.style.width = '200px';
        d.textContent = svc;
        d.onclick = () => openEventContactForm(svc, cat);
        srvList.appendChild(d);
      });
    }
  }
  function openPackageServices(pkgName, services) {
    currentEventService = "";
    document.getElementById('eventsCategoryTitle').textContent = pkgName + " Package Services";
    const srvList = document.getElementById('eventsServiceList');
    srvList.innerHTML = '';
    services.forEach(service => {
      const d = document.createElement('div');
      d.className = 'category-card';
      d.style.width = '220px';
      d.textContent = service;
      d.onclick = () => openEventContactForm(service, pkgName);
      srvList.appendChild(d);
    });
  }
  function openEventContactForm(serviceName, category) {
    currentEventService = serviceName;
    document.getElementById('eventsServiceList').style.display = 'none';
    const form = document.getElementById('eventContactForm');
    form.style.display = 'block';
    document.getElementById('eventsContactTitle').textContent = 'Contact for ' + serviceName;
    document.getElementById('eventsUserName').value = '';
    document.getElementById('eventsUserPhone').value = '';
    document.getElementById('eventsUserMessage').value = '';
    // Budget and capacity only for customized
    const cf = document.getElementById('customFields');
    if (category === 'customized') {
      cf.innerHTML = `
        <label>Budget:</label>
        <select id="eventsBudget" required>
          <option value="">Select Budget</option>
          <option>10k to 50k</option>
          <option>50k to 1L</option>
          <option>1L to 5L</option>
          <option>5L to 10L</option>
          <option>Above 10L</option>
        </select>
        <label>Capacity:</label>
        <select id="eventsCapacity" required>
          <option value="">Select Capacity</option>
          <option>5-30 people</option>
          <option>30-60 people</option>
          <option>60-90 people</option>
          <option>90-130 people</option>
          <option>Above 130 people</option>
        </select>`;
    } else {
      cf.innerHTML = '';
    }
    document.getElementById('eventsUserName').setAttribute('data-cat', category);
    document.getElementById('eventsUserName').setAttribute('data-serv', serviceName);
  }
  function backToEventsCategory() {
    document.getElementById('eventContactForm').style.display = 'none';
    document.getElementById('eventsServiceList').style.display = 'flex';
  }
  function submitEventsForm() {
    const name = document.getElementById('eventsUserName').value.trim();
    const phone = document.getElementById('eventsUserPhone').value.trim();
    const message = document.getElementById('eventsUserMessage').value.trim();
    let budget = document.getElementById('eventsBudget') ? document.getElementById('eventsBudget').value : '';
    let capacity = document.getElementById('eventsCapacity') ? document.getElementById('eventsCapacity').value : '';
    const cat = document.getElementById('eventsUserName').getAttribute('data-cat') || '';
    const serv = document.getElementById('eventsUserName').getAttribute('data-serv') || '';
    if (!name || !phone || !message) {
      alert('Please fill all required fields.');
      return;
    }
    let fullMsg = `Name: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0AService: ${encodeURIComponent(serv)}%0ACategory: ${encodeURIComponent(cat)}%0AMessage: ${encodeURIComponent(message)}`;
    if(budget) fullMsg += `%0ABudget: ${encodeURIComponent(budget)}`;
    if(capacity) fullMsg += `%0ACapacity: ${encodeURIComponent(capacity)}`;
    window.open(`https://wa.me/8977143043?text=${fullMsg}`, '_blank');
  }

  // E-commerce
  function openEcomDashboard() {
    currentEcomCategory = '';
    document.getElementById('ecomCategories').innerHTML = '';
    Object.keys(ecom).forEach(cat => {
      const d = document.createElement('div');
      d.className = 'category-card';
      d.textContent = cat;
      d.onclick = () => openEcomCategory(cat);
      document.getElementById('ecomCategories').appendChild(d);
    });
    document.getElementById('ecomCategoryContent').innerHTML = '';
    document.getElementById('ecomServiceList').innerHTML = '';
    document.getElementById('ecomOrderForm').style.display = 'none';
    showPage('ecomView');
  }
  function openEcomCategory(cat) {
    currentEcomCategory = cat;
    const content = document.getElementById('ecomCategoryContent');
    const servicesList = document.getElementById('ecomServiceList');
    content.innerHTML = `<div class="ecom-imgs">${(ecomImgs[cat] || []).map(i => `<img src="https://source.unsplash.com/150x100/?${i}" alt="${i}">`).join('')}</div>`;
    servicesList.innerHTML = '';
    (ecom[cat] || []).forEach(sub => {
      const d = document.createElement('div');
      d.className = 'service-card';
      d.textContent = sub;
      d.onclick = () => openEcomOrderForm(cat, sub);
      servicesList.appendChild(d);
    });
    document.getElementById('ecomOrderForm').style.display = 'none';
  }
  function openEcomOrderForm(cat, subcat) {
    document.getElementById('ecomOrderForm').style.display = 'block';
    document.getElementById('ecomOrderTitle').textContent = `Order ${subcat} in ${cat}`;
    document.getElementById('ecomOrderForm').onsubmit = (e) => submitOrderForm(e, cat, subcat);
  }
  function backToEcomServices() {
    document.getElementById('ecomOrderForm').style.display = 'none';
  }
  function submitOrderForm(e, cat, subcat) {
    e.preventDefault();
    const form = e.target;
    const name = form.name.value.trim();
    const phone = form.phone.value.trim();
    const orderDetails = form.orderDetails.value.trim();
    const address = form.address.value.trim();
    if(!name || !phone || !orderDetails || !address) {
      alert('All fields are required');
      return;
    }
    const msg = `Order from JKS E-commerce%0ACategory: ${cat}%0AProduct: ${subcat}%0AName: ${name}%0APhone: ${phone}%0AOrder Details: ${orderDetails}%0AAddress: ${address}`;
    window.open(`https://wa.me/8977143043?text=${encodeURIComponent(msg)}`, '_blank');
  }
  // Camera and Maps
  let currentStream = null, usingFrontCamera = true;
  function startCamera() {
    const video = document.getElementById('video');
    if(currentStream){
      currentStream.getTracks().forEach(track => track.stop());
    }
    navigator.mediaDevices.getUserMedia({video:{facingMode:usingFrontCamera?'user':'environment'}})
      .then(stream=>{
        currentStream = stream;
        video.srcObject = stream;
        video.play();
      })
      .catch(()=>alert('Camera access denied or unavailable.'));
  }
  function switchCamera() {
    usingFrontCamera = !usingFrontCamera;
    startCamera();
  }
  function capturePhoto() {
    const video = document.getElementById('video');
    const canvas = document.createElement('canvas');
    canvas.width = video.videoWidth;
    canvas.height = video.videoHeight;
    canvas.getContext('2d').drawImage(video, 0, 0);
    document.getElementById('photoOutput').innerHTML =
      `<img src="${canvas.toDataURL()}" style="max-width: 300px; border-radius: 10px;" alt="Captured photo"/>`;
  }
  function initMap() {
    new google.maps.Map(document.getElementById('map'), {
      center: {lat: 17.3850, lng: 78.4867},
      zoom: 13
    });
  }
  // Initialization
  document.addEventListener('DOMContentLoaded', () => { showPage('dashboard'); });
</script>
<script async defer src="https://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEY&callback=initMap"></script>
</body>
</html>
