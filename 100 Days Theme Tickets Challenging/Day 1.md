Hello:

I know this is likely out of scope, but they said that they had help with this prior. They would like to conditionally hide any products at checkout that are less than $0 (free). they have checkout.liquid enabled
Additional details:
They have a product which is automatically added to cart for book keeping, but don't want the customer to see this at checkout
Admin links:
https://elevate-x-5149.myshopify.com/admin/themes/128756088884?key=layout%2Fcheckout.liquid
Screenshots / video examples:
https://screenshot.click/08-29-82146-75714.png
https://screenshot.click/08-30-42677-26979.png

Plus FED - Question submission
WORKFLOW  1 hour ago
@bro
 please acknowledge that we aim for a first response within 1 week for general questions should this require escalation and merchant expectation setting. (edited) 
@bro
 clicked Acknowledge


Nicholas Bulmer
:apple:  1 hour ago
Hi Jaben, I believe this should be possible. I will check the scope in guru cards


Jaben Forbes
  1 hour ago
Hey Nicholas! Awesome thanks for that, I was never sure that checkout.liquid customisation was in scope for FED but would be good to know


Nicholas Bulmer
:apple:  1 hour ago
Many of the checkout.liquid customisations are out of scope but I think there should be a clean way to do this


Nicholas Bulmer
:apple:  1 hour ago
Im just testing a quick solution on my store


Jaben Forbes
  1 hour ago
Perfect, cheers for that Nicholas!


Nicholas Bulmer
:apple:  45 minutes ago
Would they be able to quickly test a solution?


Jaben Forbes
  45 minutes ago
Sure!


Nicholas Bulmer
:apple:  44 minutes ago
Ok so if they paste this on a new line under line 52 of their checkout.liquid it should work


Nicholas Bulmer
:apple:  44 minutes ago
<script> 
      
     `` function init(e) {
        
        {% for line_item in checkout.line_items %}
          
          {% if line_item.final_line_price == 0  %}
            let element = document.querySelector('tr[data-variant-id="{{ line_item.variant.id }}"]')
            element.style = "display: none;"
          {% endif %}
        {% endfor %}
        
      }
      document.addEventListener("page:load", init)
      document.addEventListener("page:change", init)
    </script>``


Nicholas Bulmer
:apple:  43 minutes ago
https://screenshot.click/07-45-rg5us-1no36.png
(32 kB)
https://screenshot.click/07-45-rg5us-1no36.png



Jaben Forbes
  41 minutes ago
Thanks for that! They're testing that out now


Nicholas Bulmer
:apple:  41 minutes ago
Cool I will play around on their site if it doesn’t work


Jaben Forbes
  40 minutes ago
Looks to work on my end, waiting for them to try it out now


Nicholas Bulmer
:apple:  40 minutes ago
Worked on my store as well but you never know haha


Jaben Forbes
  36 minutes ago
All working! They wanted to say thanks for your help, legend :smile:


Nicholas Bulmer
:apple:  34 minutes ago
No problem at all! It should be a pretty solid fix but if they notice the products appear when they shouldn’t make


Nicholas Bulmer
:apple:  34 minutes ago
sure they reach back out


Nicholas Bulmer
:apple:  33 minutes ago
Also something to think about that I just thought of is if they ever have script or discount that discounts a product 100% it will disappear which might not be ideal


Nicholas Bulmer
:apple:  33 minutes ago
Do they have any other way to specify it is a free gift?


Nicholas Bulmer
:apple:  32 minutes ago
Any special tags?


Jaben Forbes
  31 minutes ago
Yeah no worries, I think they understood how the checkout script worked, don't think they will be offering anything for free in the future due to their business model. I think the issue was it was necessary to bundle the products together with a bundle app so they could keep an eye on the number of rooms they would need to book for their hotels, but I'm sure they will reach out again if this poses an issue in the future


Nicholas Bulmer
:apple:  31 minutes ago
Ok too easy


Nicholas Bulmer
:apple:  31 minutes ago
<script> 
     `` function init(e) {
        {% for line_item in checkout.line_items %}
          {% if line_item.product.tags contains 'freegift'  %}
            let element = document.querySelector('tr[data-variant-id="{{ line.variant.id }}"]')
            element.style = "display: none;"
          {% endif %}
        {% endfor %}
      }
      document.addEventListener("page:load", init)
      document.addEventListener("page:change", init)``
    </script>
(edited)
:edited:
1



Nicholas Bulmer
:apple:  30 minutes ago
just in case ^^ that will hide by tags


Jaben Forbes
  30 minutes ago
They're also launching tomorrow, so I guess needed something quick as a workaround. Oh nice! So anything with a "freegift" tag won't be hidden?


Jaben Forbes
  29 minutes ago
I'll be sure to pass that on to them! Cheers for the additional help


Nicholas Bulmer
:apple:  29 minutes ago
Yeah and can be changed to whatever. Cheers Jaben!! (edited) 
