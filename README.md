# Swyfte

Swyfte is a social commerce app similar to Instagram, designed for creators and shoppers with built-in monetization, ad promotion, chat, and a marketplace.

## Product Vision
- **Social app** with image, video, reels/shorts, and messaging.
- **Creator monetization** based on real content views.
- **Marketplace** with carts, order history, and buyer/seller chat.
- **Wallet + payouts** with multi-currency support and bank withdrawals.
- **Promotion/ads tools** with demographic and location targeting.

## UI/UX Theme
- Primary theme: **white background**.
- Primary call-to-action controls: **blue buttons**.
- Home feed includes ad placements at a fixed interval of **every 3 posts**.
- Message icon placement: move to the **top-right**, next to notifications.

## Core Social Features
- User profile with:
  - Edit profile
  - Settings
  - Notifications
  - Wallet access
- Content types:
  - Image posts
  - Video posts
  - Reels/shorts section
- Video upload aspect ratios:
  - `16:9`
  - `3:4`
  - `9:16`
- Chat system:
  - App-wide user-to-user chat
  - Marketplace buyer/seller messaging routed to inbox

## Monetization Model

### Points and Revenue Rules
- Remove old point grants for:
  - Creating posts
  - Daily login
  - Watching ads
- New rule: grant points only for **post/video views**.
- Conversion: **1 point = $0.0001**.

### Creator Monetization Eligibility
Creators can monetize by either:
1. Meeting organic criteria:
   - At least **500 followers**
   - At least **1,000,000 total post/video views**
2. Paying for instant monetization:
   - **$20** one-time paid monetization option

Display these requirements on the **Monetize** screen.

### Wallet Separation
Maintain separate balances:
- **Earnings Wallet** (creator revenue from points/ad monetization)
- **Deposit Wallet** (user-funded balance for shopping and paying monetization fees)

Deposit wallet can be used for:
- Marketplace purchases
- Paid monetization fee ($20)

### Monetization and Payment Rails
- Payment methods for monetization/deposit:
  - Flutterwave
  - Stripe
  - PayPal
  - USDC
- Withdrawal options:
  - Bank transfer
  - PayPal
  - USDC
  - Stripe/Flutterwave-supported bank payouts where regionally available
- Remove **card withdrawal** feature.

### Withdrawal Bank Details
For withdrawals, collect and validate:
- Bank name
- Account name
- Account number
- Country
- Currency

## Ad Monetization and Promotions
- Integrate **Google AdMob**.
- Home feed ads display every 3 organic posts.
- Creator/user promotion tools must support targeting by:
  - Demographics
  - Locations
- Add ad promotion analytics page with:
  - Reach
  - Impressions
  - Clicks
  - Spend
  - CTR
  - Conversion (if enabled)
  - Audience/location breakdown
- Users can view performance statistics for published ads/promotions.

## Content Analytics
Provide per-post/video statistics:
- View count
- Share count
- RPM (revenue per 1,000 views)
- CPM (cost per 1,000 impressions, where applicable)
- Revenue earned

## Marketplace Features
- User-generated marketplace listings (users can upload products).
- Product purchase support:
  - Cards
  - Bank transfers
  - Wallet/deposit balance
- Cart support:
  - Add/remove items
  - Quantity updates
- Order history:
  - Status timeline
  - Payment method
  - Date and amount
- Messaging in marketplace:
  - “Message seller” opens seller inbox conversation thread.

## Currency and Exchange Rate Support
Supported currencies:
- United States Dollar (USD)
- Nigerian Naira (NGN)
- Great Britain Pounds (GBP)
- Euro (EUR)
- Ghanaian Cedi (GHS)
- South African Rand (ZAR)
- Cameroon Franc (XAF)
- Australian Dollar (AUD)
- Kenyan Shilling (KES)
- Canadian Dollar (CAD)
- Mexican Peso (MXN)

Add exchange-rate service to:
- Show conversion rates in wallet and checkout
- Normalize monetization and payout calculations
- Keep transactional records with original + converted currency values

## Suggested Backend Domain Model
- `users`
- `profiles`
- `posts`
- `videos`
- `reels`
- `post_stats`
- `wallets` (deposit_wallet, earnings_wallet)
- `wallet_transactions`
- `monetization_status`
- `creator_eligibility_metrics`
- `ad_campaigns`
- `ad_campaign_stats`
- `marketplace_products`
- `marketplace_carts`
- `marketplace_orders`
- `marketplace_order_items`
- `conversations`
- `messages`
- `bank_accounts`
- `exchange_rates`

## Delivery Checklist
- [ ] White + blue theme applied across social and marketplace flows
- [ ] Feed ad slot every 3 posts
- [ ] View-based points only (1 point = $0.0001)
- [ ] Monetize screen with 500 followers + 1M views or $20 fast-track
- [ ] Wallet split into deposit vs earnings
- [ ] Bank withdrawal fields (bank name/account name/account number/country/currency)
- [ ] Card withdrawal removed
- [ ] Buyer/seller chat and global chat enabled
- [ ] Cart and order history implemented
- [ ] Post/video analytics + ad campaign analytics pages available
- [ ] Currency list and exchange rates integrated
- [ ] Reels/shorts and required video aspect ratios supported
