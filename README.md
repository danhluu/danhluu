<h1 align="center">Hi there, I'm Luu 👋</h1> 

- 🔭 I’m currently working on [HTC](http://htc.net.vn/)
- 🌱 I’m currently learning [ASP.NET Core](https://fullstackhero.net/)
- 📫 How to reach me: [Facebook](https://www.facebook.com/jin.mitaka.1919/) | [LinkedIn](https://www.linkedin.com/in/nguy%E1%BB%85n-l%C6%B0u-1369bb169/)  
<!-- - 😄 Pronouns: ...
- ⚡ Fun fact: ... -->
const axios = require("axios")

// Retrieve existing counter and increment for this view
// See https://docs.pipedream.com/workflows/steps/code/state/
const counter = $checkpoint + 1 || 1

// Use shields.io to generate a badge with our counter as the message
const { data } = await axios({
  url: `https://img.shields.io/static/v1?label=Profile-Views&message=${counter}&color=green`,
})

// Save the incremented counter back to state
$checkpoint = counter

// See https://docs.pipedream.com/workflows/steps/triggers/#customizing-the-http-response
$respond({
  status: 200,
  headers: {
    'Content-Type': 'image/svg+xml',
    'Cache-Control': 'max-age=0, no-cache, no-store, must-revalidate'
  },
  body: data,
}) 

