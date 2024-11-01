<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">

<style type='text/css'>
	.embeddedServiceHelpButton .helpButton .uiButton {
		background-color: #016179;
		font-family: "Arial", sans-serif;
	}
	.embeddedServiceHelpButton .helpButton .uiButton:focus {
		outline: 1px solid ##016179;
	}
</style>

<script type='text/javascript' src='https://service.force.com/embeddedservice/5.0/esw.min.js'></script>
<script type='text/javascript'>
	var initESW = function(gslbBaseURL) {
		embedded_svc.settings.displayHelpButton = true; //Or false
		embedded_svc.settings.language = ''; //For example, enter 'en' or 'en-US'

		embedded_svc.settings.defaultMinimizedText = 'Chat with an Agent'; //(Defaults to Chat with an Expert)
		//embedded_svc.settings.disabledMinimizedText = '...'; //(Defaults to Agent Offline)

		//embedded_svc.settings.loadingText = ''; //(Defaults to Loading)
		//embedded_svc.settings.storageDomain = 'yourdomain.com'; //(Sets the domain for your deployment so that visitors can navigate subdomains during a chat session)

		// Settings for Chat
		//embedded_svc.settings.directToButtonRouting = function(prechatFormData) {
			// Dynamically changes the button ID based on what the visitor enters in the pre-chat form.
			// Returns a valid button ID.
		//};
		//embedded_svc.settings.prepopulatedPrechatFields = {}; //Sets the auto-population of pre-chat form fields
		//embedded_svc.settings.fallbackRouting = []; //An array of button IDs, user IDs, or userId_buttonId
		//embedded_svc.settings.offlineSupportMinimizedText = '...'; //(Defaults to Contact Us)

		embedded_svc.settings.enabledFeatures = ['LiveAgent'];
		embedded_svc.settings.entryFeature = 'LiveAgent';

    embedded_svc.settings.extraPrechatFormDetails = 
			[
				{
					"label":"Card Token",
					"value": '1234567890',
					"transcriptFields":[ "Card_Token__c" ],
					"displayToAgent":true
				},
      ];

		embedded_svc.init(
			'https://fleetcorna--amznchat.sandbox.my.salesforce.com',
			'https://fleetcorna--amznchat.sandbox.my.salesforce-sites.com/LiveChatSite',
			gslbBaseURL,
			'00DcY000000QsCt',
			'Amazon_Embedded_Chat',
			{
				baseLiveAgentContentURL: 'https://c.la2s-core2.sfdc-lywfpd.salesforceliveagent.com/content',
				deploymentId: '572cY0000006Zcb',
				buttonId: '573cY0000001nWX',
				baseLiveAgentURL: 'https://d.la2s-core2.sfdc-lywfpd.salesforceliveagent.com/chat',
				eswLiveAgentDevName: 'EmbeddedServiceLiveAgent_Parent04IcY0000007D29UAE_191d7d35c9a',
				isOfflineSupportEnabled: false
			}
		);
	};

	if (!window.embedded_svc) {
		var s = document.createElement('script');
		s.setAttribute('src', 'https://fleetcorna--amznchat.sandbox.my.salesforce.com/embeddedservice/5.0/esw.min.js');
		s.onload = function() {
			initESW(null);
		};
		document.body.appendChild(s);
	} else {
		initESW('https://service.force.com');
	}
</script>