# Easy Website Heatmap

Have you ever wanted to see how users are interacting with your website? Events are useful when you have specific elements of the site you want to track like CTAs or menu usage. It's not as helpful when you just want to see where your user is interacting on the site generally. One common solution to this challenge is using heatmaps. There are many paid tools that you can use to generate a heatmap of your website, but it's actually really easy to do it on your own using GTM, GA4, and Tableau. Here's how:

## Setting up Google Tag Manager (GTM)

GTM is a tag management tool. If you're not familiar with how tags and event tracking works on websites this demo might be a little advanced. Essentially, GTM allows you to deploy code on your website used to listen to user actions on your website. GTM then packages that information and sends it to a location of your choice. In this case we'll use GTM's native integration - GA4, but more on that in a moment.

Heatmap tracking is native to GTM, but with some pretty simple JavaScript we can collect the data we'll need. You won't need to know JS for this demo. Simply follow the steps below. 

1. Download the [GTM-Heatmap-Config](https://github.com/raahlstrom/website-heatmap/blob/75486f52e70d9b92fb8f1c5cb32f4a3da25b9744/GTM-Heatmap-Config.json) file from this repo.
2. Navigate to your GTM. You will need to have GTM deployed on your site and GA4 setup.
3. Now we're going to import the GTM-Heatmap-Config we downloaded. Click on Admin
![Step 2 screenshot](https://images.tango.us/public/edited_image_46b69f25-ba96-41b5-ac4f-e07d85858137.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&fp-z=1.0000&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
4. Click on Import Container
![Step 3 screenshot](https://images.tango.us/public/screenshot_153b6566-b490-4fc8-88a8-218faf68f979.png?crop=focalpoint&fit=crop&fp-x=0.7232&fp-y=0.6009&fp-z=2.2222&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
5. Select "GTM-Heatmap-Config.json" from file upload menu
![Step 4 screenshot](https://images.tango.us/public/screenshot_62a141e8-e325-4750-8933-9e72e5f401f4.png?crop=focalpoint&fit=crop&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
6. Click on New
![Step 5 screenshot](https://images.tango.us/public/screenshot_4cfe8e98-39fb-458d-bbb3-ea122bd49657.png?crop=focalpoint&fit=crop&fp-x=0.3385&fp-y=0.3782&fp-z=2.8402&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
7. Name your workspace
![Step 6 screenshot](https://images.tango.us/public/screenshot_e7a28ea8-74bb-4fde-8c0e-cf8c11a5943b.png?crop=focalpoint&fit=crop&fp-x=0.2669&fp-y=0.0456&fp-z=2.7389&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
8. Click on Save
![Step 7 screenshot](https://images.tango.us/public/screenshot_6cdfe19a-e537-4589-a93b-f4bd9d39c921.png?crop=focalpoint&fit=crop&fp-x=0.9576&fp-y=0.0413&fp-z=2.8712&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
9. Click on Merge. DO NOT OVERWRITE. This will delete all of your tags.
![Step 8 screenshot](https://images.tango.us/public/screenshot_817c4a7f-8e10-43e4-9212-5716a4cacc5f.png?crop=focalpoint&fit=crop&fp-x=0.3148&fp-y=0.5510&fp-z=3.0598&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
10. Click on Confirm
![Step 9 screenshot](https://images.tango.us/public/screenshot_18ebb54d-5e50-4d73-bd9f-e2fff98a4698.png?crop=focalpoint&fit=crop&fp-x=0.3417&fp-y=0.9008&fp-z=2.7119&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
11. Enter your GA4 tracking ID in the "Heatmap Track" tag.
12. Now we need to test our setup and make sure it's working. Click on Preview.
![Step 10 screenshot](https://images.tango.us/public/screenshot_5dec0822-a576-4ca0-88b2-3b1899bfc21b.png?crop=focalpoint&fit=crop&fp-x=0.8763&fp-y=0.1175&fp-z=2.8712&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
13. Click on Connect
![Step 11 screenshot](https://images.tango.us/public/screenshot_11b4ee32-59cd-4ed8-82b4-f9663a24feaa.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.7242&fp-z=2.9538&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
15. Click around on your site to ensure GTM is tracking event clicks. You'll notice that your new tag fired.
![Step 13 screenshot](https://images.tango.us/public/screenshot_e448f2a9-7f5e-47e6-8b36-de7f6de1a789.png?crop=focalpoint&fit=crop&fp-x=0.4894&fp-y=0.0954&fp-z=1.0786&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=988%3A938)
16. [Go to Tag Assistant [Connected]](https://tagassistant.google.com/#/?source=TAG_MANAGER&id=GTM-MC6F7W8&gtm_auth=TugrMWIC9Wjm9_vntcoOdQ&gtm_preview=env-15&cb=2376027123120419)
17. Open one of your events to see that the x and y coordinate values are populating.
![Step 17 screenshot](https://images.tango.us/public/screenshot_33097464-43f3-4cab-ab8f-97959e46dd4b.png?crop=focalpoint&fit=crop&fp-x=0.2677&fp-y=0.6288&fp-z=2.1239&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
18. Once your confident your tags are working click submit to publish them
![Step 18 screenshot](https://images.tango.us/public/screenshot_eacb99bd-dabe-4865-97ec-d5c21c6cd397.png?crop=focalpoint&fit=crop&fp-x=0.9469&fp-y=0.1175&fp-z=2.8712&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
19. Click on Publish
![Step 19 screenshot](https://images.tango.us/public/screenshot_f40422ce-8f69-4a43-bfae-0dbcc56fbbbe.png?crop=focalpoint&fit=crop&fp-x=0.9549&fp-y=0.0424&fp-z=2.5990&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)


## Collecting Your Data in Google Analytics 4 (GA4)
Now that GTM is collecting heatmap data we need to collect data in GA4.
1. First, we need to add our custom event dimensions to GA4. Click on Configure
![Step 1 screenshot](https://images.tango.us/public/screenshot_307c86c5-2fa2-42e3-b1c3-92a100e8ebb2.png?crop=focalpoint&fit=crop&fp-x=0.0583&fp-y=0.3868&fp-z=2.9091&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
2. Click on Custom definitions
![Step 2 screenshot](https://images.tango.us/public/screenshot_ef05dfff-8e13-45cc-801e-37aa831b792b.png?crop=focalpoint&fit=crop&fp-x=0.0906&fp-y=0.2661&fp-z=2.6158&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
3. Click on Create custom dimensions
![Step 3 screenshot](https://images.tango.us/public/screenshot_c1821ac0-a062-4601-b3b6-38d1704feba8.png?crop=focalpoint&fit=crop&fp-x=0.8953&fp-y=0.2393&fp-z=2.9161&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
4. select your x and y coordinate dimensions you made in GTM
![Step 4 screenshot](https://images.tango.us/public/screenshot_224012ad-bac7-48fd-98d8-bd4ea2cb5b55.png?crop=focalpoint&fit=crop&fp-x=0.8292&fp-y=0.5579&fp-z=3.0103&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
5. Add the dimension name
![Step 5 screenshot](https://images.tango.us/public/edited_image_5c887877-797f-4819-a87b-6ebc185f9145.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&fp-z=1.0000&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
6. Save your custom dimensions
7. Now we need to export the data so that we can visualize it. Click on reports.
![Step 7 screenshot](https://images.tango.us/public/screenshot_db2433b9-ff01-4be8-b982-b8d882c2b490.png?crop=focalpoint&fit=crop&fp-x=0.0781&fp-y=0.1931&fp-z=2.1918&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
8. Create blank report
![Step 8 screenshot](https://images.tango.us/public/screenshot_5e577824-1cf4-406e-b1cc-18a2426edf0d.png?crop=focalpoint&fit=crop&fp-x=0.2414&fp-y=0.3541&fp-z=2.1201&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
9. Name your report
![Step 9 screenshot](https://images.tango.us/public/screenshot_0593437a-45f2-43c5-beff-5c341c74b17c.png?crop=focalpoint&fit=crop&fp-x=0.0859&fp-y=0.2039&fp-z=2.6816&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
10. Click on + to add new dimensions
![Step 10 screenshot](https://images.tango.us/public/screenshot_6dfc146a-ccca-4cba-982c-528c79771e84.png?crop=focalpoint&fit=crop&fp-x=0.1615&fp-y=0.4818&fp-z=3.0103&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
11. Click on custom
![Step 11 screenshot](https://images.tango.us/public/screenshot_6d753664-be6b-42cb-bbe6-af49d6f68fbc.png?crop=focalpoint&fit=crop&fp-x=0.3820&fp-y=0.1180&fp-z=2.6704&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
12. Check your two custom dimensions
![Step 12 screenshot](https://images.tango.us/public/screenshot_5d197227-d15f-4bf3-b38d-631bed67523f.png?crop=focalpoint&fit=crop&fp-x=0.1633&fp-y=0.3117&fp-z=3.3215&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
13. Click on Import
![Step 13 screenshot](https://images.tango.us/public/screenshot_e63365bd-3b8c-46c6-a760-dfe1d4572cbc.png?crop=focalpoint&fit=crop&fp-x=0.9539&fp-y=0.0418&fp-z=3.1108&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
14. Click on + to add your metrics
![Step 14 screenshot](https://images.tango.us/public/screenshot_4bb5cd98-8f5e-412d-a041-e2a8efb33e68.png?crop=focalpoint&fit=crop&fp-x=0.1615&fp-y=0.6652&fp-z=3.0103&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
15. Click on event
![Step 15 screenshot](https://images.tango.us/public/screenshot_ca0086c6-685a-4dbe-a05d-ab96a43d3464.png?crop=focalpoint&fit=crop&fp-x=0.1635&fp-y=0.3670&fp-z=2.7444&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
16. Click on event count
![Step 16 screenshot](https://images.tango.us/public/screenshot_df96f118-528a-434b-9385-2e3e28947b67.png?crop=focalpoint&fit=crop&fp-x=0.1633&fp-y=0.4802&fp-z=3.0598&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
17. Click on Import
![Step 17 screenshot](https://images.tango.us/public/screenshot_01863a92-aaf2-459b-8c7b-4ae4dd9607cb.png?crop=focalpoint&fit=crop&fp-x=0.9539&fp-y=0.0418&fp-z=3.1108&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
18. Drag x coordinate to the "row" slot. Repeat for y.
![Step 18 screenshot](https://images.tango.us/public/edited_image_562b3280-5797-428c-88d0-f13105bec0bd.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&fp-z=1.0000&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
19. Drag event count to values slot
![Step 19 screenshot](https://images.tango.us/public/edited_image_2d6359ca-a679-4de6-acfc-b43df473a7bd.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&fp-z=1.0000&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
20. Increase show rows to the max # available
![Step 20 screenshot](https://images.tango.us/public/screenshot_d145a92e-25b1-4a46-8694-636c1f469440.png?crop=focalpoint&fit=crop&fp-x=0.3029&fp-y=0.4292&fp-z=3.1317&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
21. Click on Export data
![Step 21 screenshot](https://images.tango.us/public/screenshot_64c19bcb-9e8e-4932-9b2c-7adda9b3f7ae.png?crop=focalpoint&fit=crop&fp-x=0.8875&fp-y=0.1191&fp-z=2.7444&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)
22. Click on TSV
![Step 22 screenshot](https://images.tango.us/public/screenshot_602bf50e-87bd-456f-abca-ea0d24532a7b.png?crop=focalpoint&fit=crop&fp-x=0.9169&fp-y=0.2157&fp-z=2.9161&w=1200&mark-w=0.2&mark-pad=0&mark64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmsucG5n&ar=1920%3A932)


## Visualize Heatmap with Tableau
Now that you have your data, we can use Tableau to visualize it.
1. Clean data to remove leading rows at the top of file
2. Import data into tableau
3. Create new sheet in Tableau. Drag your y coordinate to the rows slot and your x coordinate to the columns slot.
4. Set both pills to dimensions and then set them to continuous.
5. Drag event count to color
6. In the "Marks" card, select the dropdown and select "Density"
7. Set the columns to fixed axis and set the values as 0 - 1
8. Set the rows to fixed column and set the values as 1 - 0 so that the y axis is reversed
9. Hide x and y axis names, hide all grid marks in the visualization.
10. Set the background to transparent.
11. Create a dashboard.
12. Get a screenshot of the webpage you'd like to heatmap. I use this [tool](https://www.site-shot.com/)
13. Set the dashboard dimensions to the size of your webpage.
14. Drag an image container onto the dashboard. Set your webpage as the image so that it fills the whole dashboard.
15. Drag the heatmap card you created earlier onto the dashboard as a floating conatiner.
16. Set it to the size of the dashboard.

#### Congratulations!!! You've Created a Heatmap. 

## Here is my dashboard

<div class='tableauPlaceholder' id='viz1664704139803' style='position: relative'><noscript><a href='#'><img alt='Dashboard 1 ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;my&#47;my_portfolio_heatmap&#47;Dashboard1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='my_portfolio_heatmap&#47;Dashboard1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;my&#47;my_portfolio_heatmap&#47;Dashboard1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /><param name='filter' value='publish=yes' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1664704139803');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='640px';vizElement.style.height='3347px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='640px';vizElement.style.height='3347px';} else { vizElement.style.width='100%';vizElement.style.height='727px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>
