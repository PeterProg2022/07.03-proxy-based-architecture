verwendung
	remote:
		ui:
			https://07.03-ui.vercel.app/
		api:
			curl 'https://07.03-api.vercel.app/graphql' -H 'Accept-Encoding: gzip, deflate, br' -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'Connection: keep-alive' -H 'DNT: 1' --compressed
			curl 'https://07.03-api.vercel.app/graphql' --request POST --header 'content-type: application/json'

			--data '{"query":"query {about}"}'
			--data '{"query":"mutation { setAboutMessage(message:\" Hello !\")}"}'
			--data '{"query":"query {issueList{title,created}}"}' | jq
	local:
		ui
			npm run compile
			npm run start

			http://localhost:8001/
		api
			npm run start
			curl 'localhost:4001/graphql' --request POST --header 'content-type: application/json'


cors
	geht local und remote nur mit true
