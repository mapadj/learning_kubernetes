# Helm Chart Structure

### Directory Structure

mychart/
  Chart.yaml
  values.yaml
  charts/
  templates/
  ...

### Chart.yaml 
    -> meta info about the chart
        - name
        - version
        - dependencies
        - etc

### values.yaml 
    -> values for the template files
    -> default values you can override

### chart directory
    -> chart dependencies

### template folder
    -> the actual template files

### additional files
    -> Readme
    -> License


### Commands
helm install <chartname>
helm install --values=my-values.yaml <chartname>