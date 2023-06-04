Livy is responsible for creating both the SparkApplication custom resource and the Spark context when a Spark job is submitted to Livy.

When you submit a Spark job to Livy, Livy receives the job and determines which Spark cluster should execute the job based on the Spark configuration parameters specified in the job. Livy then creates a Spark context for the job, which is used to coordinate the execution of Spark operations across the Spark cluster.

Livy also uses the Kubernetes API to create a SparkApplication custom resource in Kubernetes, which represents the Spark job that it received from Prophecy. The SparkApplication resource includes the configuration parameters for the Spark job, such as the application JAR file, the main class, and the Spark configuration properties.

The Spark Operator detects the SparkApplication resource and launches a Spark cluster to execute the job. The Spark Operator creates the necessary Kubernetes resources for the Spark cluster, such as the Spark driver and executor pods, based on the SparkApplication resource definition.

The Spark driver is responsible for coordinating the execution of Spark operations across the Spark executor pods in the cluster, and it communicates with the Spark context to do so. The Spark context, which was created by Livy, provides the programming interface for interacting with the Spark runtime and coordinating the execution of Spark operations across the Spark cluster.

So, Livy creates both the SparkApplication custom resource in Kubernetes and the Spark context, which work together to enable the execution of Spark jobs on Kubernetes using Livy and Prophecy.
