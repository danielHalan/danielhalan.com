# Daniel Halan static website

The public ASP.NET Razor portfolio has been converted to index.html, Content/Site.css and Scripts/site.js. Original artwork, text, seven projects, profile links and desktop styling are preserved. Small-screen styles and accessible image labels were added.

Open index.html directly in a browser, or upload index.html, favicon.ico, Content, Scripts and Images to any static web host. No ASP.NET, database, dependencies or build step is needed. Configure index.html as the default document.

JavaScript updates the copyright year; content and links work without JavaScript. The retired Universal Analytics script and its click handlers were removed. Several original handlers canceled navigation, so these links now open normally. External destinations retain their original URLs.

## Backend migration boundary

The original WCF ProductManager.svc is a separate desktop application service exposing GetLatestVersion, ReportError and ReportAttachment. It is not called by the portfolio and cannot receive SOAP requests, store error reports or accept attachments on a static host. Keep that service on its existing server if desktop clients still use it, or migrate it separately and update the clients.

The empty ViewAdmin.cshtml placeholder and excluded ASP.NET report viewers have no equivalent public functionality. Database files, ProductData.xml (which contains error reports), server configuration, C# sources, binaries and Photoshop source files are not included in the publishable site.

This conversion does not deploy the website or change DNS. Existing /Default.cshtml URLs need a redirect to / configured at the chosen hosting provider.