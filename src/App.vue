<script setup>
  import { AccordionComponent, ItemDirective as Item,
    ItemsDirective as Items, TreeViewComponent
  } from '@syncfusion/ej2-vue-navigations';

 const treeViewData = [
 {
      id: '01',
      name: 'Local Disk (C:)',
      subChild: [
        { id: '01-01', name: 'Program Files' },
        { id: '01-02', name: 'Users' },
        { id: '01-03', name: 'Windows' },
      ]
    },
    {
      id: '02',
      name: 'Local Disk (D:)',
      subChild: [
        { id: '02-01', name: 'Personals' },
        { id: '02-02', name: 'Projects' },
      ]
    },
    {
      id: '03',
      name: 'Local Disk (E:)',
      icon: 'folder',
      subChild: [
        {
          id: '03-01',
          name: 'Pictures',
          subChild: [
            { id: '03-01-01', name: 'Wind.jpg' },
            { id: '03-01-02', name: 'Stone.jpg' }
          ]
        },
        {
          id: '03-02',
          name: 'Documents',
          subChild: [
            { id: '03-02-01', name: 'Global Warming.ppt' },
            { id: '03-02-02', name: 'Social Network.pdf' },
          ]
        },
        {
          id: '03-03',
          name: 'Study Materials',
          subChild: [
            { id: '03-03-01', name: 'UI-Guide.pdf' },
            { id: '03-03-02', name: 'Tutorials.zip' },
          ]
        },
      ]
    }
 ];
</script>

<template>
  <div style="height:1080px; width: 500px; margin-top: 10%; margin-left: 30%;">
    <AccordionComponent expandMode="Single">
      <Items>
        <Item header="TreeView" :content="'treeview'"></Item>
        <template v-slot:treeview>
          <TreeViewComponent
            :fields="{ dataSource:treeViewData, id:'id', text:'name',
              child:'subChild'
             }"
          ></TreeViewComponent>
        </template>
        <!-- <Item header="Andrew Fuller" :content="'andrew'"></Item>
        <template v-slot:andrew>
          <div class="container" id="andrew" style="display:none">
            <img src="https://ej2.syncfusion.com/angular/demos/assets/treegrid/images/AndrewFuller.png" alt="Andrew Fuller"/>
            <div class="content">
              <b>Andrew Fuller</b> Andrew Fuller was born on Friday, 13 March 1987. Now lives in New York City, enjoys hiking, and works as a software developer at a tech startup.
            </div>
          </div>
        </template>
        <Item header="Janet Leverling" :content="'janet'"></Item>
        <template v-slot:janet>
          <div class="container" id="janet" style="display:none">
            <img src="https://ej2.syncfusion.com/angular/demos/assets/treegrid/images/JanetLeverling.png" alt="Janet Leverling"/>
            <div class="content">
              <b>Janet Leverling</b> Janet Leverling was born on Sunday, 22 July 1992. Now lives in San Francisco, loves painting, and is currently working as a marketing manager for a major retail company.
            </div>
          </div>
        </template>
        <Item header="Laura Callahan" :content="'laura'"></Item>
          <template v-slot:laura>
            <div class="container" id="laura"style="display:none">
            <img src="https://ej2.syncfusion.com/angular/demos/assets/treegrid/images/LauraCallahan.png" alt="Laura Callahan"/>
            <div class="content">
              <b>Laura Callahan</b> Laura Callahan was born on Wednesday, 15 May 1985. Now lives in Chicago, enjoys playing the guitar, and works as a financial analyst for an investment firm.
            </div>
          </div>
          </template> -->
      </Items>
    </AccordionComponent>
  </div>
</template>

<style>
  @import "../node_modules/@syncfusion/ej2-base/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-vue-navigations/styles/material.css";

  .container{
    display: inline-flex;
    width:auto;
    padding:0;
  }
  img {
    height:55px;
    width:55px;
  }
  .content{
    margin-left:10px;
  }
</style>