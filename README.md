A simple, clean theme for Roam Research:
https://www.reddit.com/r/RoamResearch/comments/gmkdxe/a_simple_cleaner_theme_for_roam/

Use a tool like [User JS and CSS](https://chrome.google.com/webstore/detail/user-javascript-and-css/nbhcbdghjpllgmfilhnhkllmkecfmpld) to inject this JS if you want to fix the sidebar:

```javascript
function addToggleClassToSidebar () {	
	var rightSidebar = document.querySelector('#roam-right-sidebar-content');
	var rightSidebarContainer = document.querySelector('#right-sidebar');	
	if( rightSidebarContainer === null )
		return;
	if( rightSidebar === null || rightSidebar.innerText === "" )
		rightSidebarContainer.classList.remove('sidebarOpen')
	else
		rightSidebarContainer.classList.add('sidebarOpen')
}
document.addEventListener('DOMContentLoaded', function () {	
	window.setInterval(addToggleClassToSidebar, 1000);
});
