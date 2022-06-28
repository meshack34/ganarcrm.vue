<template>
<div class="mynavclass"> 
      <div class="flexdisplay" >
        <div class="mylogo">
            <router-link to="/" class="navbar-item">
            <img  alt="Vue logo" 
                    src="../assets/talent.png"
                    width="100"
                    height="19">
               
            </router-link>
              
        </div>

        <div class="navbar-menu">
            <div class="navbar-end">
                <template v-if="$store.state.isAuthenticated">
                    <router-link to="/dashboard/leads" class="navbar-item">Leads</router-link>
                    <router-link to="/dashboard/clients" class="navbar-item">Clients</router-link>
                    <router-link to="/dashboard/team" class="navbar-item">Team</router-link>

                     <div @click="scroll('/')" id="course" class="flex-items dropdown navbarclass" >
                  <ul class="dropdown-menu">
                <li id="sub-dropdown" class="dropdown"><router-link to="/whyworkwithus">Why work with us<span style="margin-left: 43px;" class="glyphicon glyphicon-chevron-right"></span> </router-link>
                  <ul id="sub-dropdown-menu" class="dropdown-menu">
                    <div>
                    <div><h1>Save cost & time with our Talented team of Developers</h1></div> 
                    <div><p>Reduce development cost and leverage the vast pool of talent by offshoring</p></div>
                    </div>
                  </ul>
                </li>
                    <li><router-link to="/applications">Apply as developer</router-link></li>
                    <li><router-link to="/hiredevelopers">Hire developers</router-link></li>
                </ul>
                    
                    </div>


                </template>
    
                <div class="navbar-item">
                    <div class="buttons">
                        <template v-if="!$store.state.isAuthenticated">
                            <router-link to="/sign-up" class="button is-success"><strong>Sign up</strong></router-link>
                            <router-link to="/log-in" class="button is-light">Log in</router-link>
                        </template>

                        <template v-else>
                            <router-link to="/dashboard/my-account" class="button is-info">My account</router-link>
                        </template>
                    </div>
                </div>
            </div>
        </div>
    </div></div>
</template>

<script>
    export default {
        name: 'Navbar'
    }
</script>

<style>
 .mynavclass{ 
  padding: 2px;
    }
.mylogo{
  padding-left: 90px;
}

.flexdisplay { 
display: flex; 
background-color: aliceblue; 
align-items: center;
 } 
 .navbarclass{ 
   left: 300px;
 }
.flex-items { 
  margin: 21px;
  text-align: center; 
  
} 

.navbar-inverse{
	background-color: #2a84eb ;
	border-color: transparent;
}

.navbar-inverse .navbar-brand{
	color: #fff;
	font-size: 30px;
	margin-right: 40px;
}

#myNavbar .navbar-nav li a{
	color: #fff;
	font-size: 19px;
	}
#myNavbar #course{
	transition: all 0.3s ease-in-out;
}
#myNavbar #course:hover{
	background-color:#0751a6; 

}	
.dropdown-menu{
  display: none;
  position: absolute;
  background-color: #f0f0f0;
  box-shadow: 2px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

#sub-dropdown-menu{
display: none;
  position: absolute;
  background-color: #f0f0f0;
  margin-left: 186px;
  margin-top: -26px;

}

#sub-dropdown-menu a , .dropdown-menu a {
	color: #000 !important;
		font-size: 16px !important;
}

.dropdown:hover .dropdown-menu {display: block;transition: all 0.5s ease-in-out;}

.dropdown .dropdown-menu a:hover{background-color: #c9c7c7;}


#sub-dropdown:hover #sub-dropdown-menu {display: block;}
</style>
