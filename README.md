[![Join the chat at https://gitter.im/DemgelOpenSource/Home](https://badges.gitter.im/DemgelOpenSource/Home.svg)](https://gitter.im/DemgelOpenSource/Home?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![npm version](https://badge.fury.io/js/angular2-tabs.svg)](https://badge.fury.io/js/angular2-tabs)
[![Build Status](https://travis-ci.org/DemgelOpenSource/angular2-tabs.svg?branch=master)](https://travis-ci.org/DemgelOpenSource/angular2-tabs)
# Angular2-Tabs

Simple to use Tab option for Angular2

## Installation

Github only contains the source code for this project, to get the transpiled code for use in your project you will need to install it from npm.

Simply use the following command:

    npm install angular2-tabs --save

## Example

### Html
``` html
<an-tablist #list="anTabList" anListClass="diff-class"></an-tablist>
<an-tabs [anList]="list">
    <div *anTabDefault="tabOne">
        The Contents of Tab one
        <div anNextTab="hello">Next</div>
    </div>
    <div *anTab="'hello'">
        The Contents of Tab Two
        <div [anNextTab]="tabOne"></div>
    </div>
</an-tabs>
```
### Controller
``` ts
import {ANGULAR_TABS_DIRECTIVES, TabInterface} from "angular2-tabs/core";

@Component({
    ...
    directives: [ANGULAR_TABS_DIRECTIVES]
})
export class IndexComponent {
    tabOne: TabInterface = {id: "test", title: 'test Title', canActivate: () => {return true;}}
}
```
### Explanation (html)
#### an-tablist
The location of the TabList, this can be anywhere on the page. A local variable needs to be set, in this case `#list`. The name of `anTabList` is used.
#### an-tabs
The location that the Tabs are going to displayed. Only one will be displayed at a time.
#### anTab
A Template that contains the html that will be displayed when this tab is open.
#### anTabDefault
The default tab to be displayed. The last default tab that can be displayed (using canActivate) will be displayed when the tabs are loaded.
#### anNextTab
Directive to allow a "next" button to a Tab, must be placed within a tab. Takes either the id name as a string, or takes the `TabInterface` object used to create the Tab.
### Explanation (Controller)
#### Tab Object
In this case `tabOne` is used to be pass information to the first tab. Property `title` is the title of the tab, and will be displayed in the tabList. The `canActivate` property is a function used to determine if a tab can be displayed.
## CSS
You will need to customize the list using your own CSS. The list will recieve either `an-tablist` or a custom class name defined with `anListClass`.
### an-active / an-inactive
(added to Tab-list only only)
These classes are added to the `li`.
### an-canactivate / an-cantactivate
(added to both Tab-list and anNextTab tags) 
These classes are added to the `li` based on if the tab can be activated based on the `canActivate` function passed in.

## Contributing

To contribute, please fork this repository, then clone your repository. Once cloned feel free to make any changes you like.

When you clone the repository, you will only recieve the Typescript files, typings and tsconfig. There is no testing included, as this is pretty simple.

## Thanks
A Special thanks to those at `Angular2` for creating angular2.