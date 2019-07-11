try
{
    node('master')
    {
        
    }    
    stage('build') {
        step {
             echo "Stage2: Hello World!"
        }
    }
    stage('stage2') {
        step {
            echo "Stage2: Hello World!"
        }
    }    
}
catch (e)
{
    echo 'The Pipeline failed :('    
    throw e
}
finally
{
    stage('Build Naming')
    {
        node('master')
        {
            currentBuild.displayName = "#${BUILD_NUMBER}  "
        }
    }
    script 
    {
        manager.addShortText("Test pipeline \u2705", "black", "lightgreen", "0px", "white")
        echo "${manager.build.getResult()}"
        manager.build.setResult(hudson.model.Result.SUCCESS)
        if(manager.build.getResult() != hudson.model.Result.SUCCESS)
        {
            echo "Failure"
        }
        else
        {
            echo "Success"
        }
    }
}
