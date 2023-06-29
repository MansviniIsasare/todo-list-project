pipeline
{
	agent 
	{
		label
		{
			label "built-in"
			customWorkspace "/mnt/workspace"
		}
	}
	
	
	stages
	{
		stage('clone-repo')
		{
			steps
			{
				git credentialsId: 'github-jenkins', url: 'https://github.com/Mansvini-Isasare/node-todo-cicd.git'
			}
		}
		stage('deploy')
		{
			docker build . -t node-app-todo
			docker run -d --name node-app-container -p 8000:8000 node-app-todo

		}
	}
}
