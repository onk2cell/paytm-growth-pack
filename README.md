# Paytm Growth Pack: AI Soundbox demo

A clickable hackathon demo of **Growth Pack**, a new skill for the Paytm AI Soundbox. A small shop asks the Soundbox for customers. The AI then runs a margin-safe offer for people shopping nearby, and the Soundbox announces when an offer customer pays.

> Demo only. It has no backend, no login and no real payments. All data is mock data kept in the browser.

## Run it

Open `index.html` in Chrome or Brave. It needs no install, no build and no internet.

Keyboard shortcuts: **1–4** switch screens. **↺ Reset demo** clears everything.

## The four screens

| # | Screen | What it shows |
|---|--------|---------------|
| 1 | **Merchant: Soundbox assistant** | A chat with a mic. The merchant asks "How was my week?" and gets a sales summary. They ask for new customers and the AI proposes ₹20 off on bills over ₹200, with a maximum cost of ₹600 and new customers only. After **Approve**, the offer shows as live to about 840 nearby shoppers. "How did the offer go?" returns the results. |
| 2 | **Customer: phone** | A Paytm payment-success screen. While the offer is live, an offer card appears below it. **Use offer** goes to the shop counter. |
| 3 | **Shop payment and Soundbox** | Bill ₹240, discount ₹20, amount to pay ₹220. **Pay** updates the results and the Soundbox says in Hindi: *"Paytm offer se naya customer aaya. 220 rupaye prapt hue."* |
| 4 | **Admin panel** | Live KPIs, campaigns by locality with an AI-moderation column, and rule toggles: one offer per user per day, category blocking and a discount cap. Changing a rule changes what customers see straight away. |

## Demo click path (about 2 minutes)

1. **Reset demo**
2. Screen 1: "How was my week?", then "I need more new customers", then **Approve**
3. Screen 2: the offer card appears. Tap **Use offer**
4. Screen 3: **Pay ₹220**. The Soundbox announces the payment
5. Screen 1: "How did the offer go?" shows 1 redemption
6. Screen 4: the numbers have gone up. Lower the discount cap below ₹20 and the offer is flagged and hidden from customers

## Privacy by design

- Merchants see **totals only** (for example "~840 shoppers within 300 m"). They never see names, phone numbers or other shops' sales.
- Matching happens inside Paytm and is based on location, not purchase history.
- Customers see why an offer is shown and can turn off nearby offers.

## Safety and margin guardrails

- The offer's maximum cost is fixed up front, and the offer auto-pauses when the budget is used up.
- The minimum bill is set above the shop's average bill, so the larger basket covers the discount.
- Admin rules cover one offer per user per day, blocked categories (tobacco, alcohol) and a discount cap.

## Tech

A single `index.html` file with plain HTML, CSS and JavaScript and no dependencies. It uses the browser's speech synthesis for the Hindi announcement and speech recognition for the mic where available. Where recognition isn't available (for example in Brave or offline), the mic types the next scripted question instead.

## Ideas for next steps

- Replace the scripted AI replies with a real model call that uses the shop's sales history.
- Add more shop categories with tuned offers.
- Add Hindi voice input.

*No Paytm logo or brand assets are used. This is a concept demo.*
