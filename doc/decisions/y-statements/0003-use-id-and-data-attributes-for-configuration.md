**In the context** of injecting configuration into the tracking consent snippet (PLATUI-775 and PLATUI-649),  
**facing** not wanting to duplicate knowledge of the platform and tracking consent url structure, 
delivering a simple, easily testable solution and
delivering a solution that works on IE    
**we decided to** use data attributes for configuration parameters and to use an identifier to locate the tracking consent
 SCRIPT tag  
**and neglected** using regular expression pattern matching on the SCRIPT src attribute,  
**to achieve** a flexible DRY solution that will withstand changes to url paths, port numbers,
and platform environment naming  
**accepting** service developers will need to add this identifier to the SCRIPT tag albeit with the
 assistance of a helper
