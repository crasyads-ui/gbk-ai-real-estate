# GBK AI Real Estate — V12 Voice + Listen + Explain

Mobile-first GBK AI Real Estate PWA based on V10, with the existing responsive/global-language frontend preserved.

## V11 changes
- Connected the property discovery UI to the production GBK Real Estate API.
- Property cards now load from Supabase-backed `re_properties` data instead of hard-coded cards.
- Hero **Ask GBK AI** now performs a live property search and queues an AI advisor request.
- Rental Finder now searches the live property API with location, property type and budget range.
- Property enquiry forms now submit to the secure backend and return an enquiry reference.
- Added API-ready favorite endpoint for the authenticated account layer.
- Added backend tables for properties, enquiries, search events and AI requests.
- Added six API seed listings for integration testing; they are explicitly marked as GBK demo/illustrative data.
- Existing GBK registration, Share & Earn, subscription payment/status, PWA install, country/currency and multilingual UI are preserved.

## Backend API
Supabase Edge Function:
`https://yjwgnapymqetxvksqacd.supabase.co/functions/v1/real-estate-api`

Actions:
- `health`
- `search`
- `listing`
- `enquiry`
- `ai-request`
- `favorite`

The property database is intentionally RLS-enabled and accessed through the Edge Function. Production/licensed property feeds can be connected to `re_properties` later without changing the frontend contract.

## Important
The seeded listings are **illustrative integration data**, not verified live property inventory. Production listings, prices, availability, legal records and verification should come from approved/licensed sources.
