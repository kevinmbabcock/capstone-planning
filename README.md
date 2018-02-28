## Kevin Babcock

## B.Carchano Art

# Project Description

### Goals

 * This project is designed to help the artist feature her works online. It will feature the artist herself and all of her works, both those available for sale and recently sold. Those interested in purchasing her works or seeking more information will be able to contact her through the site.

##### Home page:
 * User should be able to navigate to view for works, contact, and bio from navigation bar
 * User should be able to select a medium from a drop-down menu for works NavBar link
 * User should see featured photos on the home page one at a time, switching at intervals
 * If Admin is logged in, NavBar should include Admin link to Admin tools

##### Works view:
 * User should be able to view all works for sale and all recently sold works in a list
 * User should be able to sort works by medium
 * User should be able to sort works by for sale or sold
 * User should be able to click on a specific work to enlarge
 * User should be able to hover over the image to have additional details appear
 * User should be able to click on 'next' and 'prev' links to scroll through master works list in enlarged view
 * User should be able to inquire about purchasing the item, and be navigated to contact page with details of desired work

##### Contact view:
 * User should be able to fill out a form with their name, email, and inquiry
 * On submission, user should see a confirmation that their inquiry was successful
 * If routed through work details inquiry link, user should see the details of that work, and details should be submitted with form

##### Bio view:
 * User should see a description of the artist (provided by artist)
 * User should be able to navigate to artist's Instagram page though link

##### Admin
 * Admin should be able to add works to the app
 * Admin should be able to edit the details of all works in the list
 * Admin should be able to select which works appear on the home page
 * Admin should be able to sort works by all properties, and only view desired works
 * Admin should be able to edit bio
 * Admin should be able to view a list of all inquiries

### MVP
 * Works, contact, and bio link fully functional with correct routing
 * All works on properly displayed in relevant view
 * Work detail appear when work is clicked on
 * User is able to scroll through works one at a time
 * Featured works appear on home page, one at a time, rotating at intervals
 * User is able to filter works by medium
 * User is able to submit contact form, and admin receives submitted form
 * Admin is able to add/edit works and Bio

### Tools & Technologies
 * React
 * Redux
 * Firebase
 * HTML
 * CSS

##### API's
 * Shipping cost

### Additional Features
 * PayPal (API) integration to purchase directly from the site
 * Use pop-up window to display enlarged photo with work details
 * Integrate scroll option in pop-up window

### State

##### Redux Store
 * work: WorksListContainer --> WorkDetails/Contact
  - title: string
  - height: number
  - width: number
  - medium: string
  - price: number
  - forSale: boolean
  - featured: boolean
  - id: uuid
 * selectedWork: work.id (WorkDetails --> Contact/ScrollButtons)
 * workType: [acryllic, waterColor, ink, all] (NavBar --> WorksListContainer)
 * purchaseInquiry: boolean (WorkDetails --> Contact)

##### Local UI State
 * NavBar (isAdmin: boolean)
 * Contact (formSubmitted: boolean)

### Component Tree
  - App
    - Header
    - NavBar
      - WorksLink
      - ContactLink
      - BioLink
      - AdminLink
    - Contact
      - ContactForm
      - ContactVerification
      - InstagramLink
    - Bio/About
      - InstagramLink
    - Carousel
      - WorksListContainer
        - WorksList
         - Works
          - WorkDetails
    - WorksListContainer
      - WorksList
        - Works
          - WorkDetails
            - Contact
              - ShippingCost
            - ScrollButtons
    - Admin
      - AddWork
        - AddWorkForm
      - WorksListContainer  
        - WorksList
          - EditCarousel
          - Works
            - EditWorkDetails
      - EditBio      
        - EditBioForm
      - InquiriesListContainer
        - InquiriesList
          - Inquiry
            - InquiryDetails
    - LogIn        
