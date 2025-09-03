[hysyssolutiondemo-3f10-ml] Details
============================

Generated On: 2025-09-03 12:37:19 UTC

TML Solution DAG Parameters' Details: User Chosen Parametets
----------------------------

STEP 1: Get TML Core Params: `tml_system_step_1_getparams_dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_1_getparams_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - solutionname
     - hysyssolutiondemo-3f10-ml
   * - solutiontitle
     - TML HYSYS Solution: Oil and Gas Demo
   * - solutiondescription
     - This solution is using TML to process data from HYSYS and Perform Entity-Based Machine Learning for Each Well
   * - brokerhost
     - pkc-3w22w.us-central1.gcp.confluent.cloud:9092
   * - brokerport
     - 
   * - cloudusername
     - None
   * - ingestdatamethod
     - LOCALFILE
 
STEP 2: Create Kafka Topics: `tml_system_step_2_kafka_createtopic_dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_2_kafka_createtopic_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - companyname
     - Otics
   * - myname
     - Sebastian
   * - myemail
     - Sebastian.Maurice
   * - mylocation
     - Toronto
   * - replication
     - 3
   * - numpartitions
     - 3
   * - enabletls
     - 1
   * - microserviceid
     - 
   * - raw_data_topic
     - hysys-data
   * - preprocess_data_topic
     - hysys-preprocess
   * - ml_data_topic
     - ml-data
   * - prediction_data_topic
     - hysys-gas-predictions

STEP 3: `Produce to Kafka Topics <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_read_LOCALFILE_step_3_kafka_producetotopic_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - PRODUCETYPE
     - LOCALFILE
   * - inputfile
     - 
   * - TOPIC
     - hysys-data
   * - PORT
     - _39399
   * - IDENTIFIER
     - TML solution,
   * - HTTPADDR
     - https://
   * - FROMHOST
     - ('seb', '127.0.1.1')
   * - TOHOST
     - 0.0.0.0
   * - CLIENTPORT
     - Not Applicable
   * - TSS_CLIENTPORT
     - Not Applicable
   * - TML_CLIENTPORT
     - Not Applicable
   * - docfolder
     - 
   * - doctopic
     - 
   * - chunks
     - 0
   * - docingestinterval
     - 0

STEP 4: Preprocesing Data: `tml-system-step-4-kafka-preprocess-dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_4_kafka_preprocess_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - hysys-data
   * - preprocess_data_topic
     - hysys-preprocess
   * - preprocessconditions
     - 
   * - delay
     - 70
   * - maxrows
     - 800
   * - array
     - 0
   * - saveasarray
     - 1
   * - topicid
     - -999
   * - rawdataoutput
     - 0
   * - asynctimeout
     - 120
   * - timedelay
     - 0
   * - preprocesstypes
     - avg
   * - pathtotmlattrs
     - --pathtotmlattrs--
   * - identifier
     - TML Hysys Solution Demo
   * - jsoncriteria
     - uid=Datapoint.WellId,filter:allrecords~subtopics=Datapoint.Children.Vapor1.Name,Datapoint.Pressure.Unit,Datapoint.Children.Choke.Name,Datapoint.Children.V200.Name,Datapoint.Children.V200.Temperature.Unit,Datapoint.Children.Pic100.Name,Datapoint.Children.Lic101.Name~values=Datapoint.Children.Vapor1.GasFlowRate.Value,Datapoint.Pressure.Value,Datapoint.Children.Choke.OutletPressure.Value,Datapoint.Children.V200.Pressure.Value,Datapoint.Children.V200.Temperature.Value,Datapoint.Children.Pic100.SetPoint.Value,Datapoint.Children.Lic101.SetPoint.Value~identifiers=Datapoint.Children.Vapor1.Name,Datapoint.Pressure.Unit,Datapoint.Children.Choke.Name,Datapoint.Children.V200.Name,Datapoint.Children.V200.Temperature.Unit,Datapoint.Children.Pic100.Name,Datapoint.Children.Lic101.Name~datetime=Metadata.SecondsTimestamp~msgid=Metadata.Id~latlong=

STEP 4a: Preprocesing Data: `tml-system-step-4a-kafka-preprocess-dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_4a_kafka_preprocess_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - --raw_data_topic1--
   * - preprocess_data_topic
     - --preprocess_data_topic1--
   * - preprocessconditions
     - --preprocessconditions1--
   * - delay
     - --delay1--
   * - maxrows
     - --maxrows1--
   * - array
     - --array1--
   * - saveasarray
     - --saveasarray1--
   * - topicid
     - --topicid1--
   * - rawdataoutput
     - --rawdataoutput1--
   * - asynctimeout
     - --asynctimeout1--
   * - timedelay
     - --timedelay1--
   * - preprocesstypes
     - --preprocesstypes1--
   * - pathtotmlattrs
     - --pathtotmlattrs1--
   * - identifier
     - --identifier1--
   * - jsoncriteria
     - --jsoncriteria1--

STEP 4b: Preprocesing Data: `tml-system-step-4b-kafka-preprocess-dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_4b_kafka_preprocess_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - --raw_data_topic2--
   * - preprocess_data_topic
     - --preprocess_data_topic2--
   * - preprocessconditions
     - --preprocessconditions2--
   * - delay
     - --delay2--
   * - maxrows
     - --maxrows2--
   * - array
     - --array2--
   * - saveasarray
     - --saveasarray2--
   * - topicid
     - --topicid2--
   * - rawdataoutput
     - --rawdataoutput2--
   * - asynctimeout
     - --asynctimeout2--
   * - timedelay
     - --timedelay2--
   * - preprocesstypes
     - --preprocesstypes2--
   * - pathtotmlattrs
     - --pathtotmlattrs2--
   * - identifier
     - --identifier2--
   * - jsoncriteria
     - --jsoncriteria2--

STEP 4c: Preprocesing Data: `tml-system-step-4c-kafka-preprocess-dag  <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_4c_kafka_preprocess_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - --raw_data_topic3--
   * - preprocess_data_topic
     - --preprocess_data_topic3--
   * - delay
     - --delay3--
   * - maxrows
     - --maxrows3--
   * - array
     - --array3--
   * - saveasarray
     - --saveasarray3--
   * - topicid
     - --topicid3--
   * - rawdataoutput
     - --rawdataoutput3--
   * - asynctimeout
     - --asynctimeout3--
   * - timedelay
     - --timedelay3--
   * - searchterms
     - --rtmssearchterms--
   * - rtmsstream
     - --rtmsstream--
   * - identifier
     - --identifier3--
   * - rememberpastwindows
     - --rememberpastwindows--
   * - patternwindowthreshold
     - --patternwindowthreshold--
   * - localsearchtermfolder
     - --localsearchtermfolder--
   * - localsearchtermfolderinterval
     - --localsearchtermfolderinterval--
   * - rtmsscorethreshold
     - --rtmsscorethreshold--
   * - rtmsscorethresholdtopic
     - --rtmsscorethresholdtopic--
   * - attackscorethreshold
     - --attackscorethreshold--
   * - attackscorethresholdtopic
     - --attackscorethresholdtopic--
   * - patternscorethreshold
     - --patternscorethreshold--
   * - patternscorethresholdtopic
     - --patternscorethresholdtopic--
   * - rtmsfoldername
     - --rtmsfoldername--
   * - rtmsmaxwindows
     - --rtmsmaxwindows--
   * - RTMS Output Github Link
     - `Output Data URL <--rtmsoutputurl-->`_

STEP 5: Entity Based Machine Learning : `tml-system-step-5-kafka-machine-learning-dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_5_kafka_machine_learning_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - preprocess_data_topic
     - hysys-preprocess
   * - ml_data_topic
     - ml-data
   * - modelruns
     - 80
   * - offset
     - -1
   * - islogistic
     - 0
   * - networktimeout
     - 600
   * - modelsearchtuner
     - 90
   * - processlogic
     - 
   * - dependentvariable
     - Vapor-1_preprocessed_Avg
   * - independentvariables
     - psia_preprocessed_Avg,Choke_preprocessed_Avg,V-200_preprocessed_Avg,F_preprocessed_Avg,PIC-100_preprocessed_Avg,LIC-101_preprocessed_Avg
   * - rollbackoffsets
     - 450
   * - topicid
     - -999
   * - consumefrom
     - 
   * - fullpathtotrainingdata
     - /rawdata/viper-ml/hysys
   * - transformtype
     - 
   * - sendcoefto
     - 
   * - coeftoprocess
     - 
   * - coefsubtopicnames
     - 
   * - ML Output Github Link
     - `Output Data URL <https:\/\/github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/mldata/hysys>`_

STEP 6: Entity Based Predictions: `tml-system-step-6-kafka-predictions-dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_6_kafka_predictions_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - preprocess_data_topic
     - hysys-preprocess
   * - ml_prediction_topic
     - hysys-gas-predictions
   * - streamstojoin
     - psia_preprocessed_Avg,Choke_preprocessed_Avg,V-200_preprocessed_Avg,F_preprocessed_Avg,PIC-100_preprocessed_Avg,LIC-101_preprocessed_Avg
   * - inputdata
     - 
   * - consumefrom
     - ml-data
   * - offset
     - -1
   * - delay
     - 70
   * - usedeploy
     - 1
   * - networktimeout
     - 600
   * - maxrows
     - 800
   * - topicid
     - -999
   * - pathtoalgos
     - /rawdata/viper-ml/hysys

STEP 7: Real-Time Visualization: `tml-system-step-7-kafka-visualization-dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_7_kafka_visualization_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - vipervizport
     - 49689
   * - topic
     - iot-preprocess,iot-ml-prediction-results-output
   * - dashboardhtml
     - iot-failure-machinelearning.html
   * - secure
     - 1
   * - offset
     - -1
   * - append
     - 0
   * - chip
     - amd64
   * - rollbackoffset
     - 400

STEP 8: `tml_system_step_8_deploy_solution_to_docker_dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_8_deploy_solution_to_docker_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - Docker Container
     - maadsdocker/hysyssolutiondemo-3f10-ml-amd64 (https://hub.docker.com/r/maadsdocker/hysyssolutiondemo-3f10-ml-amd64)
   * - Docker Run Command
     - docker run -d --net=host -p 5050:5050 -p 4040:4040 -p 6060:6060 \
          --env TSS=0 \
          --env SOLUTIONNAME=hysyssolutiondemo-3f10-ml \
          --env SOLUTIONDAG=solution_preprocessing_ml_dag-hysyssolutiondemo-3f10 \
          --env GITUSERNAME=<Enter Github Username> \
          --env GITPASSWORD='<Enter Github Password>' \          
          --env GITREPOURL=<Enter Github Repo URL> \
          --env SOLUTIONEXTERNALPORT=5050 \
          -v /var/run/docker.sock:/var/run/docker.sock:z \
          -v /your_localmachine/foldername:/rawdata:z \
          --env CHIP=amd64 \
          --env SOLUTIONAIRFLOWPORT=4040 \
          --env SOLUTIONVIPERVIZPORT=6060 \
          --env DOCKERUSERNAME='' \
          --env EXTERNALPORT=39399 \
          --env KAFKABROKERHOST=127.0.0.1:9092 \                    
          --env KAFKACLOUDUSERNAME='<Enter API key>' \
          --env KAFKACLOUDPASSWORD='<Enter API secret>' \          
          --env SASLMECHANISM=PLAIN \                    
          --env VIPERVIZPORT=49689 \
          --env MQTTUSERNAME='' \
          --env MQTTPASSWORD='' \          
          --env AIRFLOWPORT=9000 \
          --env READTHEDOCS='<Enter Readthedocs token>' \ 
          maadsdocker/hysyssolutiondemo-3f10-ml-amd64

STEP 9: `tml_system_step_9_privategpt_qdrant_dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_9_privategpt_qdrant_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - PrivateGPT Container
     - --pgptcontainername--
   * - PrivateGPT Run Command
     - --privategptrun--
   * - Qdrant Container
     - --qdrantcontainer--
   * - Qdrant Run Command
     - --qdrantrun--
   * - Consumefrom
     - 
   * - pgpt_data_topic
     - --pgpt_data_topic--
   * - offset
     - -1
   * - rollbackoffset
     - 400
   * - topicid
     - -999
   * - enabletls
     - 1
   * - partition
     - --partition--
   * - prompt
     - --prompt--
   * - context
     - --context--
   * - jsonkeytogather
     - --jsonkeytogather--
   * - keyattribute
     - --keyattribute--
   * - keyprocesstype
     - --keyprocesstype--
   * - vectordbcollectionname
     - --vectordbcollectionname--
   * - concurrency
     - --concurrency--
   * - CUDA_VISIBLE_DEVICES
     - --cuda--
   * - pgpthost
     - --pgpthost--
   * - pgptport
     - --pgptport--
   * - hyperbatch
     - --hyperbatch--
   * - docfolder
     - --docfolder--
   * - docfolderingestinterval
     - --docfolderingestinterval--
   * - useidentifierinprompt
     - --useidentifierinprompt--
   * - searchterms
     - --searchterms--
   * - streamall
     - --streamall--
   * - temperature
     - --temperature--
   * - vectorsearchtype
     - --vectorsearchtype--
   * - llm
     - --llmmodel--
   * - embedding
     - --embedding--
   * - vectorsize
     - --vectorsize--
   * - contextwindowsize
     - --contextwindowsize--
   * - vectordimension
     - --vectordimension--
   * - mitrejson
     - --mitrejson--

STEP 10: `tml_system_step_10_documentation_dag <https://github.com/smaurice101/raspberrypitss/tree/main/tml-airflow/dags/tml-solutions/hysyssolutiondemo-3f10/tml_system_step_10_documentation_dag-hysyssolutiondemo-3f10.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - Solution Documentation URL
     - https://hysyssolutiondemo-3f10-ml.readthedocs.io
