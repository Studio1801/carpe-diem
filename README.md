# Carpe Diem Cafe & Wine Bar: demo site

Demo website and owner dashboard for Carpe Diem (812 Jefferson St, Lafayette, LA). Everything is demo: nothing is sent anywhere, and no links leave the page.

## What's in the folder

- `index.html`: the whole site, with its styles and code in one file
- `img/`: photos and the white logo, from carpediemcafeandwinebar.com and their Instagram (get the owner's OK before going live)
- `video/`: four short Instagram clips for the slideshow under the hero, re-encoded for the web, each with a poster frame

To preview it, open `index.html` in a browser.

## How it works now (demo)

- All data is saved in the visitor's own browser (localStorage, under the key `cd-demo-v2`). This covers orders, gelato flavours, cake and catering requests, events, newsletter sign-ups, price changes and shop settings.
- The website and the dashboard read the same saved data. Place an order on the site, then open `#owner` (the "Owner dashboard" link in the footer) and the order is there.
- "Reset the demo" in Shop settings puts back the example data.
- Phone, email, Instagram and Maps links show a "Demo: ..." message instead of leaving the page. The click handler for this sits just above `load(); renderAll(); route();` at the end of the script.

## Features

**Customer side**
- Order ahead: + buttons on the menu, a cart, pickup times worked out from the opening hours (Lafayette time), pay at pickup, and a live order tracker
- Today's gelato case, set by the owner
- Cake and catering request form, with a reference number (C-xxxx)
- Events with seat reservations
- Newsletter sign-up
- Banner across the top for notices
- Sun and moon path in the hero, and an automatic switch to night mode after 5 PM

**Owner dashboard (`#owner`)**
- Orders board: New, Making, Ready, Picked up, plus today's sales
- Gelato case editor
- Cakes and catering: enter a quote, set the status
- Events: publish an event, see the guest list
- Menu and prices: mark items sold out, edit prices
- Newsletter list, with a "copy all emails" button
- Shop settings: banner, pause online orders, closed today

## To turn it into the real thing

1. Replace the browser storage with a real database. The `load()`, `save()` and `commit()` functions in the script are the only places that read and write data. You could use a Google Sheet with Apps Script, as on the Miss Oz site.
2. Add a real owner login in front of `#owner`. It's open in the demo on purpose.
3. Send a text when an order is marked Ready, for example with Twilio.
4. Email the shop when a new order, request or RSVP comes in, for example with Resend.
5. Optional: online payment through Square or Stripe.
6. Restore the real phone, email, Instagram and Maps links by removing the demo click handler.

## Content to check with the client

- Menu and prices were read from their current menu images. The white wine is printed as "Bourdeaux Rouge" but described as a white, so it's listed here as Bordeaux Blanc.
- These are sample data and need replacing: the two events (marked "Example"), the example orders and requests, and the cake sizes and serving counts.
- The 2014 avocado basil award and the gelato flavours come from press coverage.
- Hours: Mon 8-8, Tue to Fri 8-9, Sat 9-9, Sun 9-8.
