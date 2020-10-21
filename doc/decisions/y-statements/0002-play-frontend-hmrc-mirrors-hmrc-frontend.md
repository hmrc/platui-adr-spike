**In the context of** providing an HMRC footer translated into Welsh,  
**facing** the lack of support for Welsh in the GDS govukFooter component (PLATUI-752),  
**we decided to** maintain parity between hmrc-frontend and play-frontend-hmrc
with the exception of helper components that will not contain significant presentational markup.  
**and against** adding localised content to the existing hmrcFooter helper component in play-frontend-hmrc using Play
I18n support (draft PR https://github.com/hmrc/play-frontend-hmrc/pull/25)  
**to achieve** separation of concerns for play-frontend-hmrc, conceptual integrity for play-frontend-hmrc and
ability to test markup using the existing framework  
**accepting that**  
we will need to add and maintain a new hmrcFooter component in hmrc-frontend and 
play-frontend-hmrc providing a mirror of govukFooter with localised content,  
the new hmrcFooter component will not be able to make use of any Play I18n features,  
we will need to create a new helpers package within play-frontend-hmrc to clearly demarcate them
from presentational components,  
we will need to redesign the existing hmrcFooter helper to wrap the new hmrcFooter component
 and move to the helpers package,  
the new hmrcFooter component will need to be deprecated when GDS provide a localised version
of govukFooter,  
we will need to liaise and get approval from the HMRC design system team for adding
hmrcFooter to the hmrc/design-system and hmrc/hmrc-frontend  
we will be adding features that are unlikely to be useful or used by designers because
 at the prototyping phase content is not stable enough for translation into Welsh  
**because** we want hmrc-frontend to be the source of truth for presentational markup and maintain
separation of concerns between hmrc-frontend and play-frontend-hmrc
