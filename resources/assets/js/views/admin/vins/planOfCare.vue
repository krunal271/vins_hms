<template>
<div class="container">
	<div class="page-header">
		<div class="row">
			<div class="col-md-6">
				<h1>Plan of Care</h1>
			</div>
			<div class="col-md-6">
				<div class="text-right">
					DOC NO. F/IPD/48 <br>
					REV. No. 0.2 <br>
					WEF 31-01-2015
				</div>
			</div>
		</div>
	</div>

	<hr>

	<form method="post">
		<div class="row form-group">
			<div class="col-md-6">
					<div class="col-md-6">
					<label>Ipd No : </label>
				</div>
				<div class="col-md-6">
					<input class="form-control" type="text" name="ipd_no" v-model="ipd_id" v-validate="'required'" />
					<span class="help is-danger" v-show="errors.has('ipd_no')">
									Room number is required
								</span>
				</div>
			</div>
			<div class="col-md-6">
			<div class="col-md-6">
				<label>Diagnosis</label>
			</div>
			<div class="col-md-6">
				<input class="form-control" type="text" name="diagnosis" value="" v-model ="planOfCare.diagnosis"/>
			</div>
		</div></div>

	<div class="row form-group">
			<div class="col-md-6">
				<label>Patient's Needs and Treatment Goals : </label>
			</div>
			<div class="col-md-6">
				<input class="form-control" type="text" name="needs_goals" value="" v-model ="planOfCare.needs_goals"/>
			</div>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<label>Treatment Plan : </label>
			</div>
			<div class="col-md-6">
				<input class="form-control" type="text" name="treatment_plan" value="" v-model ="planOfCare.treatment_plan"/>
			</div>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<label>Preventive Aspects : </label>
			</div>
			<div class="col-md-6">
				<textarea class="form-control" name="preventive_aspects" value=""  value="" v-model ="planOfCare.preventive_aspects"></textarea>
			</div>
		</div>

		<div class="row form-group">
			<table class="table table-bordered">
				<thead>
					<tr>
						<th>Sr No</th>
						<th>Progress</th>
						<th>Date</th>
					</tr>
				</thead>
				<tbody>
					<tr v-for="n in 8">
						<td>{{n}} </td>
						<td>
							<input class="form-control" type="text" :name="'progress_'+n" value="" v-model="planOfCare.Plan_Of_Care[n].progress" v-validate="'required'"/>
							<span class="help is-danger" v-show="errors.has('progress_'+n)">
								Progress is required
							</span>
						</td>
						<td>
							<input class="form-control" type="date" :name="'date_'+n" value="" v-model="planOfCare.Plan_Of_Care[n].date" v-validate="'required'"/>
							<span class="help is-danger" v-show="errors.has('date_'+n)">
								Progress is required
							</span>
						</td>
					</tr>


				</tbody>
			</table></div>

			<div class="row form-group">
				<div class="col-md-6">
					<label>Note on Discharge : </label>
				</div>
				<div class="col-md-6">
					<textarea class="form-control" name="note_discharge" value="" v-model ="planOfCare.note_discharge"></textarea>
				</div>
			</div>
		</div-->

		<div class="row form-group">
			<div class="col text-center">
				<button class="btn btn-success" type="button" @click="savePlanOfCare()">Submit</button>
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
							'type': 'planOfCare',
							'patient_id': this.$store.state.Patient.patientId,
							'ipd_id': this.$store.state.Patient.ipdId,
							'planOfCare' : {
								'diagnosis': '',
								'needs_goals': '',
								'treatment_plan': '',
								'preventive_aspects': '',
								'note_discharge': '',
									'Plan_Of_Care': {
										'1': {
											'progress': '',
											'date': '',


										},
										'2': {
											'progress': '',
											'date': '',

										},

										'3': {
											'progress': '',
											'date': '',

										},
										'4': {
											'progress': '',
											'date': '',

										},
										'5': {
											'progress': '',
											'date': '',

										},
										'6': {
											'progress': '',
											'date': '',

										},
										'7': {
											'progress': '',
											'date': '',

										},
										'8': {
											'progress': '',
											'date': '',

										},


									}

							}
					}
			},
			methods: {
			GetSelectComponent(componentName) {
				 this.$router.push({name: componentName})
			},
				savePlanOfCare() {
					this.$validator.validateAll().then(
	            (response) => {
	            	if (!this.errors.any()) {
	            		 $("body .js-loader").removeClass('d-none');
	            		 var planOfCareData = {'type':this.type,'patient_id':this.patient_id,'ipd_id':this.ipd_id,'form_data':this.planOfCare};
                   User.savePlanOfCare(planOfCareData).then(
                         (response) => {
                         	console.log(response)
                         	if(response.data.status == 200) {
                         		toastr.success('Plan Of Care  has been saved', 'planOfCare', {timeOut: 5000});
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
