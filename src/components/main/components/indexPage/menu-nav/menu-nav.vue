<template>
       <Menu mode="horizontal" theme="dark" active-name="indexPage" ref="indexPage">
          <div class="layout-logo"></div>
          <div class="layout-nav">
            <MenuItem name="1-2">
              <Icon type="ios-grid"></Icon>
              <span>首页</span>
            </MenuItem>
            <Submenu name="1">
              <template slot="title">
                <Icon type="ios-navigate"></Icon>客户管理
              </template>
              <MenuItem name="company_table_page"><router-link to='/company_table_page'>企业列表</router-link></MenuItem>
              <MenuItem name="disable_table_page"><router-link to='/disable_table_page'>停用列表</router-link></MenuItem>
            </Submenu>
            <Submenu name="2">
              <template slot="title">
                <Icon type="ios-keypad"></Icon>批量申报
              </template>
              <MenuItem name="taxDeclare"><router-link to='/taxDeclare'>税款申报</router-link></MenuItem>
              <MenuItem name="checkPass"><router-link to='/checkPass'>检查通过</router-link></MenuItem>
              <MenuItem name="zeroDeclare"><router-link to='/zeroDeclare'>零申报</router-link></MenuItem>
            </Submenu>
            <Submenu name="3">
              <template slot="title">
                <Icon type="ios-analytics"></Icon>汇算清缴
              </template>
              <MenuItem name="3-1">Option 1</MenuItem>
              <MenuItem name="3-2">Option 2</MenuItem>
            </Submenu>
            <Submenu name="3">
              <template slot="title">
                <Icon type="ios-cog"></Icon>基础设置
              </template>
              <MenuItem name="departmentManagement"><router-link to='/departmentManagement'>部门管理</router-link></MenuItem>
              <MenuItem name="roleManagement"><router-link to='/roleManagement'>角色管理</router-link></MenuItem>
            </Submenu>
          </div>
        </Menu>
</template>
