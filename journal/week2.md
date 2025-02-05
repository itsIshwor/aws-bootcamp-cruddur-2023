# Week 2 — Distributed Tracing

- On week's start I was able to setup telemetry tool honeycomb.

  - First logged into honeycomb and generated the API key
  - After that added all the required setup to docker compose file for backend setup
  - added required dependencies on requirements.txt
  - docker compose on sent traces to honeycomb, on first data sent I got email that traces has been sent
    ![First command](/journal/assets/honey-comb-local-setup.png)

    ![First command](/journal/assets/lconsole-telmentry-log.png)

    ![First command](/journal/assets/honecomb-successfully-setup-email.png)

    ![First command](/journal/assets/honeycomb-homepage-total%20scanned.png)

    ![First command](/journal/assets/honeycomb-showing-traces.png)

    ![First command](/journal/assets/docker-container-running-2.png)

    ![First command](/journal/assets/open-telemetry-logs-details.png)

- command use for setup x-ray group.
  `sh
    aws configure set region us-east-2 &&
    aws xray create-group \
--group-name "x-ray-group-setup" \
--filter-expression "service(\"backed-flask\")" 
    `

  ```sh
      aws xray create-sampling-rule --cli-input-json file://json/x-ray.json
  ```

  ![First command](/journal/assets/seeting-aws-xray-group-from-cli.png)

  ![First command](/journal/assets/seeting-aws-xray-group-from-cli.png)

  ![First command](/journal/assets/creating-sampling-rule-cli.png)

  ![First command](/journal/assets/sending-batch%20to%20x-ray%20from%20app.png)

  ![First command](/journal/assets/1.404Errorview-X-ray.png)

  ![First command](/journal/assets/1.404Errorview-X-ray.png)

  ![First command](/journal/assets/200Ok%20view%20on%20x-ray.png)

  ![First command](/journal/assets/list-of-traces-x-ray.png)
