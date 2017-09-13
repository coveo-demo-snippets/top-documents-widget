# top-documents-widget

This widget displays all the top Documents in your Lightning community.

1. Create the custom component listed here
2. Create a new page
  - If you run into an issue where you have a blank component after changing the page name, please follow this procedure:
    - In Developer Console, run this query: SELECT Id, CoveoV2__Configuration__c,     CoveoV2__SiteName__c FROM CoveoV2__CoveoLightningSettings__c
    - Select the JSON and copy it into a separate file
    - Copy the existing page (usually communityCoveo) and its settings and add it as another key:value in the Json
    - Paste it back in the Developer Console
    - Save Rows
   
3. In Preview mode, click on Edit on the component and go to the Code View. Paste the following: (You may need to change the data-data-expression to reflect your actual filetypes. Not you will no longer have access to the Interface Editor....

```
    <div id="searchTopDocs" class="CoveoSearchInterface" data-design="new" data-results-per-page="5" 
         data-expression="(@filetype==pdf) OR (@filetype==&quot;YouTubeVideo&quot;)" data-pipeline="recommendations">
        <div class="CoveoAnalytics"></div>
        <div class="coveo-main-section">
            <div class="coveo-results-column">
                <div class="CoveoHiddenQuery"></div>
                <div class="CoveoErrorReport" data-pop-up="false"></div>
                <div class="CoveoResultList" data-layout="list" data-wait-animation="fade" data-auto-select-fields-to-include="true">
                    <script id="Default" class="result-template" type="text/html" data-layout="list"><div class="coveo-result-frame" style="padding-top:10px;">
                            <div class="coveo-result-row">
                                <div class="coveo-result-cell" style="width:64px; text-align:center; padding-top:10px; vertical-align:top"> 
                                    <span class="CoveoIcon" data-small="false" data-with-label="true"></span> 
                                </div>
                                <div class="coveo-result-cell" style="padding-left:10px; padding-top:15px">
                                    <div class="coveo-result-row">
                                        <div class="coveo-result-cell" style="font-size:16px"><span class="CoveoSalesforceResultLink"></span>

<div class="CoveoQuickview">
                                                <div class="coveo-icon-for-quickview"></div>
                                            </div></div><div class="coveo-result-cell" style="font-size:16px"><span class="CoveoText" data-value="Source:"></span>
<span class="CoveoFieldValue" data-field="@source"></span></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </script>
                </div>
            </div>
        </div>
    </div>
    ```
    
