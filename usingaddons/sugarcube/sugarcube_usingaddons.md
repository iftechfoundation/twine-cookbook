# "Using Add-ons": SugarCube (v2.18)

## Summary

Many people have developed external add-ons for use in story formats like SugarCube. Often, these add-ons will come with instructions that should be followed to incorporate them into a story.

This example uses the [&lt;&lt;cyclinglink&gt;&gt;](https://www.motoslave.net/sugarcube/2/#downloads) macro created by Thomas Michael Edwards based on the work done by Leon Arnott for Twine 1. It's code was copied into the Story JavaScript for use in the story.

## Twee Code

```
:: StoryTitle
Using Add-ons in SugarCube

:: UserScript[script]
/*! <<cyclinglink>> macro for SugarCube 2.x */
!function(){"use strict";if("undefined"==typeof version||"undefined"==typeof version.title||"SugarCube"!==version.title||"undefined"==typeof version.major||version.major<2)throw new Error("<<cyclinglink>> macro requires SugarCube 2.0 or greater, aborting load");version.extensions.cyclinglinkMacro={major:3,minor:3,revision:2},macros.cyclinglink={handler:function(a,b,c){function toggleText(w){w.classList.remove("cyclingLinkInit"),w.classList.toggle(rl+"Enabled"),w.classList.toggle(rl+"Disabled"),w.style.display="none"===w.style.display?"inline":"none"}var rl="cyclingLink";switch(c[c.length-1]){case"end":var end=!0;c.pop();break;case"out":var out=!0;c.pop()}var v=null;c.length&&"$"===c[0][0]&&(v=c[0].slice(1),c.shift());var h=State.variables;if(!out||!v||""!==h[v]){var l=insertElement(a,"a");l.className="link-internal cyclingLink",l.setAttribute("data-cycle",0);for(var i=0;i<c.length;i++){var on=i===(v?Math.max(c.indexOf(h[v]),0):0),d=insertElement(null,"span",null,"cyclingLinkInit cyclingLink"+(on?"En":"Dis")+"abled");on?(v&&(h[v]=c[i]),l.setAttribute("data-cycle",i)):d.style.display="none",insertText(d,c[i]),on&&end&&i===c.length-1?l.parentNode.replaceChild(d,l):l.appendChild(d)}jQuery(l).ariaClick(function(){var t=this.childNodes,u=this.getAttribute("data-cycle")-0,m=t.length;if(toggleText(t[u]),u+=1,out&&u===m?v&&(h[v]=""):(u%=m,v&&(h[v]=c[u])),(end||out)&&u===m-(end?1:0)){if(!end)return void this.parentNode.removeChild(this);var n=this.removeChild(t[u]);return n.className=rl+"End",n.style.display="inline",void this.parentNode.replaceChild(n,this)}toggleText(t[u]),this.setAttribute("data-cycle",u)})}}}}();

:: Start
<<cyclinglink "First" "Second" "Third">>

```
