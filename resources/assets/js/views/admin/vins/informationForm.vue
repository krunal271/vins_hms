<template>
<div class="container">
	<div class="page-header">
		<div class="row">
			<div class="col-md-6">
			<h1>Information Form</h1>
			</div>
			<div class="col-md-6">
				<div class="text-right">
					DOC NO. F/IPD/27 <br>
					REV. No. 0.0 <br>
					WEF 01-08-2013
				</div>
			</div>
		</div>
	</div>

	<hr>

	<form action="" method="post">
    <div class="row form-group">
      <div class="col-md-6">
        <div class="col-md-6">
          <label for="date">Date:</label>
        </div>
        <div class="col-md-6">
					<input class="form-control" type = "date" v-validate="'required'" id = "date" name="date" value=""  v-model="informationFormData.date"/>
					<span class="help is-danger" v-show="errors.has('date')">
										Field is required
									</span>

        </div>
      </div>
      <div class="col-md-6">
        <div class="col-md-6">
          <label for="time">Time:</label>
        </div>
        <div class="col-md-6">
					<input class="form-control" type = "time" v-validate="'required'" id = "time" name="time" value=""  v-model="informationFormData.time"/>
					<span class="help is-danger" v-show="errors.has('time')">
										Field is required
									</span>

        </div>
      </div>
    </div>

    <hr>
		<div class="row form-group">
			<h3>Patient information given by Patient himself / Relative of Patient</h3>
		</div>

	  <table class="table table-bordered">
	    <thead>
			  <tr>
  				<th>Sr. No.</th>
  				<th>Contents</th>
  				<th>Response</th>
			  </tr>
			</thead>
			<tbody>
			  <tr>
			    <td>1</td>
					<td>Do you get pain in chest of breathlessness on walking or after exertion?

					</td>
					<td>
							 <select class="form-control" v-validate="'required'" id = "_00" name="_00" value=""  v-model="informationFormData._00">
								<option value="Yes">Yes</option>
								<option value="No">No</option>
							</select>
							<span class="help is-danger" v-show="errors.has('_00')">
                        Field is required
                      </span>
					</td>

			  </tr>

			  <tr>
		    <td>2</td>
				<td>Have you suffered in past from high blood pressure, heart disease or angina?

				</td>
					<td>
							 <select class="form-control" v-validate="'required'" id = "_01" name="_01" value=""  v-model="informationFormData._01">
								<option value="Yes">Yes</option>
								<option value="No">No</option>
							</select>
							<span class="help is-danger" v-show="errors.has('_01')">
                Field is required
              </span>
					</td>
			 </tr>

			  <tr>
			    <td>3</td>
  				<td>
  					Have you been treated in past or at present for any major illness? If yes, please specify:
						<input class="form-control" type = "text" id = "major_illness" name="major_illness" value=""  v-model="informationFormData.major_illness"/>
  				</td>
  					<td>
  							 <select class="form-control" v-validate="'required'" id = "_02" name="_02" value=""  v-model="informationFormData._02">
  								<option value="Yes">Yes</option>
  								<option value="No">No</option>
  							</select>
								<span class="help is-danger" v-show="errors.has('_02')">
	                        Field is required
	                      </span>
  					</td>
			  </tr>

			  <tr>
			    <td>4</td>
  				<td>Have you ever suffered from any previous nervous disorders convulsions or paralysis before?

  				</td>
  					<td>
  							 <select class="form-control" v-validate="'required'" id = "_03" name="_03" value=""  v-model="informationFormData._03">
  								<option value="Yes">Yes</option>
  								<option value="No">No</option>
  							</select>
								<span class="help is-danger" v-show="errors.has('_03')">
	                        Field is required
	                      </span>
  					</td>
			  </tr>

			  <tr>
			    <td>5</td>
  				<td>Do you have a disorder of bleeding or clotting of blood?

  				</td>
  					<td>
  						<div class="form-group">
  							 <select class="form-control" v-validate="'required'" id = "_04" name="_04" value=""  v-model="informationFormData._04">
  								<option value="Yes">Yes</option>
  								<option value="No">No</option>
  							</select>
								<span class="help is-danger" v-show="errors.has('_04')">
	                        Field is required
	                      </span>
  						</div>
  					</td>
			  </tr>

			  <tr>
			    <td>6</td>
  				<td>
  					Have you been treated for diabetes?

  				</td>
  					<td>
  						<div class="form-group">
  							 <select class="form-control" v-validate="'required'" id = "_05" name="_05" value=""  v-model="informationFormData._05">
  								<option value="Yes">Yes</option>
  								<option value="No">No</option>
  							</select>
								<span class="help is-danger" v-show="errors.has('_05')">
	                        Field is required
	                      </span>
  						</div>
  					</td>
			  </tr>

			  <tr>
			    <td>7</td>
  				<td>
  					Do you have a history of Peptic Ulcer or hyper acidity?

  				</td>
  					<td>
  						<div class="form-group">
  							 <select class="form-control" v-validate="'required'" id = "_06" name="_06" value=""  v-model="informationFormData._06">
  								<option value="Yes">Yes</option>
  								<option value="No">No</option>
  							</select>
								<span class="help is-danger" v-show="errors.has('_06')">
	                        Field is required
	                      </span>
  						</div>
  					</td>
			  </tr>

			  <tr>
			    <td>8</td>
  				<td>
  					Do you suffer from any allergy or drug hypersensitivity?

  				</td>
  					<td>
  						<div class="form-group">
  							 <select class="form-control" v-validate="'required'" id = "_07" name="_07" value=""  v-model="informationFormData._07">
  								<option value="Yes">Yes</option>
  								<option value="No">No</option>
  							</select>
								<span class="help is-danger" v-show="errors.has('_07')">
	                        Field is required
	                      </span>
  						</div>
  					</td>

			  </tr>

			  <tr>
			    <td>9</td>
  				<td>
  					Do you suffer from Asthama / breathing difficulty?

  				</td>
  					<td>
  						<div class="form-group">
  							 <select class="form-control" v-validate="'required'" id = "_08" name="_08" value=""  v-model="informationFormData._08">
  								<option value="Yes">Yes</option>
  								<option value="No">No</option>
  							</select>
								<span class="help is-danger" v-show="errors.has('_08')">
	                        Field is required
	                      </span>
  						</div>
  					</td>

			  </tr>

			  <tr>
			    <td>10</td>
  				<td>Have you had difficulty in passing urine in the past?

  				</td>
  					<td>
  						<div class="form-group">
  							<select class="form-control" name="_09" v-model="informationFormData._09" v-validate="'required'">
  								<option value="Yes">Yes</option>
  								<option value="No">No</option>
  							</select>
								<span class="help is-danger" v-show="errors.has('_09')">
	                        Field is required
	                      </span>
  						</div>
  					</td>
			  </tr>

        <tr>
			    <td>11</td>
  				<td>Have you been operated in the past?
            <div class="">
              If yes, please specify:
            </div>
              <div class="col-md-6">
								<input class="form-control" type = "text" id = "operated_in_past" name="operated_in_past" value=""  v-model="informationFormData.operated_in_past"/>
              </div>

            <ul>
              <li>Did you have any anesthetic or surgical complication?</li>
              <li>Did you receive any blood transfusion?</li>
            </ul>
  				</td>
					<td>
						<div class="form-group">
							 <select class="form-control" v-validate="'required'" id = "_10" name="_10" value=""  v-model="informationFormData._10">
								<option value="Yes">Yes</option>
								<option value="No">No</option>
							</select>
							<span class="help is-danger" v-show="errors.has('_10')">
                        Field is required
                      </span>
						</div>
            <div class="form-group">
							 <select class="form-control" v-validate="'required'" id = "_10a" name="_10a" value=""  v-model="informationFormData._10a">
								<option value="Yes">Yes</option>
								<option value="No">No</option>
							</select>
							<span class="help is-danger" v-show="errors.has('_10a')">
                        Field is required
                      </span>
						</div>
            <div class="form-group">
							 <select class="form-control" v-validate="'required'" id = "_10b" name="_10b" value=""  v-model="informationFormData._10b">
								<option value="Yes">Yes</option>
								<option value="No">No</option>
							</select>
							<span class="help is-danger" v-show="errors.has('_10b')">
                        Field is required
                      </span>
						</div>
					</td>
			  </tr>

        <tr>
			    <td>12</td>
  				<td>
            Are you taking any drugs at present?
            <div class="">
              If yes, give details:
            </div>
            <div class="row form-group">
              <div class="col-md-6">
								<input class="form-control" type = "text" id = "taking_drugs_at_present" name="taking_drugs_at_present" value=""  v-model="informationFormData.taking_drugs_at_present"/>
              </div>
            </div>

  				</td>
					<td>
						<div class="form-group">
							 <select class="form-control" v-validate="'required'" id = "_11" name="_11" value=""  v-model="informationFormData._11">
								<option value="Yes">Yes</option>
								<option value="No">No</option>
							</select>
							<span class="help is-danger" v-show="errors.has('_11')">
                        Field is required
                      </span>
						</div>
					</td>
			  </tr>
			</tbody>
	  </table>

    <div class="row form-group">
			<div class="col">
				<div class="row">
					<div class="col-md-6">
						<label for="name_of_patient">Name of Patient:</label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type = "text" v-validate="'required'" id = "name_of_patient" name="name_of_patient" value=""  v-model="informationFormData.name_of_patient"/>
						<span class="help is-danger" v-show="errors.has('name_of_patient')">
							Field is required
						</span>
					</div>
				</div>
			</div>
			<div class="col">
				<div class="row">
					<div class="col-md-6">
						<label for="name_of_relative">Name of Relative:</label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type = "text" v-validate="'required'" id = "name_of_relative" name="name_of_relative" value=""  v-model="informationFormData.name_of_relative"/>
						<span class="help is-danger" v-show="errors.has('name_of_relative')">
							Field is required
						</span>
					</div>
				</div>
			</div>
    </div>

		<div class="row form-group">
			<div class="col text-center">
				<button class="btn btn-success" type="button" @click="saveInformationForm()">Submit</button>
			</div>
		</div>
	</form>
</div>
</template>


<script >
	import User from '../../../api/users.js';
    export default {
        data() {
            return {
                'footer' : 'footer',
                'currentYear': new Date().getFullYear(),
                'informationFormData' : {
									'date':'',
									'time':'',
									'_00':'',
									'_01':'',
									'major_illness':'',
									'_02':'',
									'_03':'',
									'_04':'',
									'_05':'',
									'_06':'',
									'_07':'',
									'_08':'',
									'_09':'',
									'operated_in_past':'',
									'_10':'',
									'_10a':'',
									'_10b':'',
									'taking_drugs_at_present':'',
									'_11':'',
									'name_of_patient':'',
									'name_of_relative':''
                }
            }
        },
        methods: {
		    GetSelectComponent(componentName) {
		       this.$router.push({name: componentName})
		    },
		    saveInformationForm() {
		    	this.$validator.validateAll().then(
	            (response) => {
	            	if (!this.errors.any()) {
	            		 $("body .js-loader").removeClass('d-none');
				    	User.saveInformationForm(this.informationFormData).then(
		                (response) => {
		                	if(response.data.code == 200) {
		                		toastr.success('Information Form has been saved', 'Information Form', {timeOut: 5000});
		                	}
		                	 $("body .js-loader").addClass('d-none');

		                },
		                (error) => {
		                	 $("body .js-loader").addClass('d-none');

		                }
		                )
			    	}
			    },
                (error) => {
                }
                )

			}
		  },

    }
</script>
