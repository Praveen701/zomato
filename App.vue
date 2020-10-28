<template>
<body>
    <div>
        <div class="cont">
   <h1>Add a restaurant</h1><br>
 
    
    <form >
  <div class="form-row ">
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputEmail4">Restaurant Name<span style="color: red;">*</span></label>
      <input type="text" class="form-control"  placeholder="Restaurant Name">
      <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Owner Name<span style="color: red;">*</span></label>
      <input type="text" class="form-control"  placeholder="Owner Name">
    <span class="validation" >We will miss you</span>
    </div>
  </div>
  <div class="form-row">
    <div class="form-group col-sm-12 col-md-6 mt-2">
     <label for="inputState">Restaurant POC Designation<span style="color: red;">*</span></label>
      <select id="inputState" class="form-control">
        <option selected>Choose...</option>
        <option>...</option>
      </select>
        <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Owner Contact Number<span style="color: red;">*</span></label>
      <input type="text" class="form-control"  placeholder="Owner Contact Number">
    <span class="validation" >We will miss you</span>
    </div>
    
  </div>
   <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Owner Email ID<span style="color: red;">*</span></label>
      <input type="email" class="form-control" id="" placeholder="Owner Email ID">
     <span class="validation" >We will miss you</span>
    </div>
     <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputState">Restaurant City<span style="color: red;">*</span></label>
      <select id="inputState" class="form-control">
        <option selected>Restaurant City</option>
        <option>Chennai</option>
      <option>Salem</option>
       <option>Bangalore</option>
      </select>
    <span class="validation" >We will miss you</span>
   </div>
   </div>

    <div class="form-row">
 
   
    <div class="form-group col-sm-12 col-md-6 mt-2">
     <label for="inputState">GSTIN Present<span style="color: red;">*</span></label>
      <select id="inputState" class="form-control">
        <option selected>GSRIN Present</option>
        <option>...</option>
      </select>
        <span class="validation" >We will miss you</span>
          </div>
      <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Restauraunt GSTIN<span style="color: red;">*</span></label>
      <input type="text" class="form-control"  placeholder="Restauraunt GSTIN">
  <span class="validation" >We will miss you</span>
    </div>
   </div>
   <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Restaurant/Trade Name<span style="color: red;">*</span></label>
      <input type="text" class="form-control" placeholder="Restaurant/Trade Name">
      <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Business Entity Name<span style="color: red;">*</span></label>
      <input type="text" class="form-control" id="inputPassword4" placeholder="Business Entity Name">
     <span class="validation" >We will miss you</span>
    </div>
   </div>
   <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Registration Date<span style="color: red;">*</span></label>
      <input type="date" class="form-control"  placeholder="Date">
      <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Business Type<span style="color: red;">*</span></label>
      <input type="text" class="form-control" placeholder="Business Type">
     <span class="validation" >We will miss you</span>
    </div>
   </div>
   <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">GST State<span style="color: red;">*</span></label>
      <input type="text" class="form-control"  placeholder="GST State">
      <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">GST Type<span style="color: red;">*</span></label>
      <input type="text" class="form-control" id="inputPassword4" placeholder="GST Type">
      <span class="validation" >We will miss you</span>
    </div>
   </div>
   <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">City/Town<span style="color: red;">*</span></label>
      <input type="text" class="form-control" id="inputPassword4" placeholder="City/Town">
     <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-md-7">
      <div id="app">
            <GmapMap v-bind:center="myCoordinates"
                v-bind:zoom="7"
                 map-type-id="roadmap"
                 style="width: 700px; height: 300px"
                    ref="mapRef"
            @dragend="handleDrag"
                 >

                    <GmapMarker ref="myMarker"
                            v-bind:key="index"
                            v-for="(m, index) in markers"
                           v-bind:position="m.position"
                        v-bind:clickable="true"
                      v-bind:draggable="true"
                    @click="center=m.position">
                </GmapMarker>
      </GmapMap>
    </div>
    </div>
   </div>
   <!-- map ends -->
    <div class="form-row">
  
    <div class="form-group col-md-6 latlng">
      <label for="inputPassword4">Latitude<span style="color: red;">*</span>      <p>{{ mapCoordinates.lat }} </p></label>
 
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Longitude<span style="color: red;">*</span></label>
        <p>{{ mapCoordinates.lng }} </p>
    </div>
   </div>
      <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Address<span style="color: red;">*</span></label>
      <input type="text" class="form-control"  placeholder="Address">
      <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Postal Code<span style="color: red;">*</span></label>
      <input type="number" class="form-control"  placeholder="Postal Code">
     <span class="validation" >We will miss you</span>
    </div>
   </div>
    <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputPassword4">Swiggy State<span style="color: red;">*</span></label>
      <input type="text" class="form-control"  placeholder="Swiggy State">
      <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputState">Is this in a mall or a building complex?<span style="color: red;">*</span></label>
      <select id="inputState" class="form-control">
        <option selected></option>
        <option>Mall</option>
        <option>Building complex</option>
      </select>
      <span class="validation" >We will miss you</span>
    </div>
   </div>
   
   <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
      <label for="inputState">Floor Number<span style="color: red;">*</span></label>
      <select id="inputState" class="form-control">
        <option selected>0</option>
        <option>1</option>
        <option>2</option>
        <option>3</option>
        <option>4</option>
      </select>
     <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
     <label for="inputPassword4">Building/Mall Name<span style="color: red;">*</span></label>
      <input type="text" class="form-control"  placeholder="Building/Mall Name">
      <span class="validation" >We will miss you</span>
    </div>
   </div>
   <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
 <label for="inputPassword4">Landmark<span style="color: red;">*</span></label>
      <input type="text" class="form-control" id="inputPassword4" placeholder="Landmark">
      <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
     <label for="inputPassword4">FSSAI Licence number<span style="color: red;">*</span></label>
      <input type="text" class="form-control" id="inputPassword4" placeholder="FSSAI Licence number">
    <span class="validation" >We will miss you</span>
    </div>
   </div>
   <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
 <label for="inputPassword4">FSSAI Registered Number<span style="color: red;">*</span></label>
      <input type="number" class="form-control" id="inputPassword4" placeholder="FSSAI Registered Number">
     <span class="validation" >We will miss you</span>
    </div>
    <div class="form-group col-sm-12 col-md-6 mt-2">
     <label for="inputPassword4">FSSAI Expiry Date<span style="color: red;">*</span></label>
      <input type="date" class="form-control" id="inputPassword4" placeholder="Password">
     <span class="validation" >We will miss you</span>
    </div>
   </div>
   <div class="form-row">
  
    <div class="form-group col-sm-12 col-md-6 mt-2">
 <label for="inputPassword4">Address on FSSAI<span style="color: red;">*</span></label>
      <input type="text" class="form-control" id="inputPassword4" placeholder="Address on FSSAI">
      <span class="validation" >We will miss you</span>
    </div>
   

    </div>
   <div class="form-row">
               <div class="form-group col-sm-12 col-md-6 mt-2">
 <label for="inputPassword4">Upload KYC(Aadhar card/Passport/Driving Licence/Voter ID)
   <span style="color: red;">*</span> <b>(Please upload [".png",".jpg",".jpeg"]images)</b></label>
      
    <!-- Plain mode -->
    <b-form-file v-model="file2" class="mt-3" plain></b-form-file>
    <div class="mt-3">Selected file: {{ file ? file.name : '' }}

      </div>  <span class="validation" >We will miss you</span><br>

  </div>
  <div class="form-group col-md-7">
 <label for="inputPassword4">GSTIN Certificate Upload
   <span style="color: red;">*</span> </label>
      
    <!-- Plain mode -->
    <b-form-file v-model="file2" class="mt-3" plain></b-form-file>
    <div class="mt-3">Selected file: {{ file ? file.name : '' }}

      </div>
        <span class="validation" >We will miss you</span><br>

  </div>
  <div class="form-group col-md-7">
 <label for="inputPassword4">FSSAI Certificate Upload
   <span style="color: red;">*</span>  </label>
      
    <!-- Plain mode -->
    <b-form-file v-model="file2" class="mt-3" plain></b-form-file>
    <div class="mt-3">Selected file: {{ file ? file.name : '' }}

      </div>

  </div>
   </div>  <span class="validation" >We will miss you</span><br>
      <b-button variant="success" class="form-group col-sm-12 col-md-6 mt-2"><b>SUBMIT</b></b-button>
  
   
    </form>
        </div>
  </div>
</body>
</template>

<script>
import {gmapApi} from 'vue2-google-maps'
export default {
  name: 'App',
  data() {
      return{
             center: { lat: 13.0827, lng: 80.2707},
             file2: null,
          
                map: null,
                myCoordinates: {
                    lat: 0,
                    lng: 0
                },
                zoom: 7
            }
        },
     
        created() {
            // does the user have a saved center? use it instead of the default
            if(localStorage.center) {
                this.myCoordinates = JSON.parse(localStorage.center);
            } else {
                // get user's coordinates from browser request
                this.$getLocation({})
                    .then(coordinates => {
                        this.myCoordinates = coordinates;
                    })
                    .catch(error => alert(error));
            }
            // does the user have a saved zoom? use it instead of the default
            if(localStorage.zoom) {
                this.zoom = parseInt(localStorage.zoom);
            }
        },
        mounted() {
            // add the map to a data object
            this.$refs.mapRef.$mapPromise.then(map => this.map = map);
        },
        methods: {
           markers: [ {
             position: {lat: 13.0827, lng: 80.2707}
                    }       ],
        
            handleDrag() {
                // get center and zoom level, store in localstorage
                let center = {
                    lat: this.map.getCenter().lat(),
                    lng: this.map.getCenter().lng()
                };
                let zoom = this.map.getZoom();
                localStorage.center = JSON.stringify(center);
                localStorage.zoom = zoom;
            }
        },
        computed: {
            mapCoordinates() {
                if(!this.map) {
                    return {
                        lat: 0,
                        lng: 0
                    };
                }
                return {
                    lat: this.map.getCenter().lat().toFixed(4),
                    lng: this.map.getCenter().lng().toFixed(4)
                }
            },
            
       
          
          
            }


        
}

</script>


<style>
 body {
    margin: 0%;
    font-family: -apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol,Noto Color Emoji;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    color:black;
    text-align: left;
    background-color: whitesmoke;
}
.cont{
    margin: 2% 8%;
}
.form-control {
    display: block;
    width: 63%;
    height: calc(1.5em + 0.75rem + 2px);
    padding: 0.375rem 0.75rem;
    font-size: 1rem;
    margin: 0px 0px;
    font-weight: 400;
    line-height: 1.5;
    color: #495057;
    background-color: #fff;
    background-clip: padding-box;
    border: 1px solid #ced4da;
    border-radius: 0.25rem;
    -webkit-transition: border-color 0.15s ease-in-out, -webkit-box-shadow 0.15s ease-in-out;
    transition: border-color 0.15s ease-in-out, -webkit-box-shadow 0.15s ease-in-out;
    transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
    transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out, -webkit-box-shadow 0.15s ease-in-out;
}
.validation {
    color: red;
    font-size: small;
}
input, button, select, optgroup, textarea {
    margin: 0 3%;
    font-family: inherit;
    font-size: inherit;
    line-height: inherit;
}
.latlng{
  display: inline;
}

</style>
