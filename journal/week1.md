# Week 1 — App Containerization

- build command to build the images using following command:

    ```sh
    docker build -t flask-backend .
    ```

- after this I am able to see following images on my docker desktop

    ![docker images](/journal/assets/docker-images.png)

- tried to run diffrent variteis of command on vs code terminal in order to run
the docker images we built for flask app. The final version which worked is:

    ```sh
    docker run --rm -p 4567:4567 -it  -e FRONTEND_URL='*' -eBACKEND_URL='*' flask-backend
    ```

    ![First command](/journal/assets/docker-container-running-2.png)

    ![second command](/journal/assets/docker-container-running-1.png)

- There after created the docker compose file on frist attempt to run the

    ```sh
    docker compose up
    ```

- it was failing because of COPY layer error in ``Dockerfile` for frontend-react-js due to wrong directory I forget to update.

    ![Failing command](/journal/assets/docker-compose-failing.png)

- later on checking the Dockerfile I found that,
I forget to update the coopy commmand from
`COPY src target` to
`COPY . /frontend-react-js`. Once I changed this, I was able to run everything as expcted.

- After that I was able to run the docker compose using `docker compose up` command
and able to see following logs on console and docker desktop.

    ![Failing command](/journal/assets/docker-compose-up-1.png)
    
    ![Failing command](/journal/assets/docker-compose-desktop-view.png)

- Also finished setting up snyk tool on my local using brew with command 
    ```sh
        brew tap snyk/tap
        brew install snyk
    ```   
    - created accound for snyk at [snyk.io](https://snyk.io/)   
    - Authenticated the  the tool using command 
        ```sh 
            snyk auth
        ```
    - After that I tried to  genrated the reports for the cotnainer containers we created during week-1. Using following command and reports are generated as follows:
      - backed synk result:
        ![Failing command](/journal/assets/synk%20-flask-container-scan.png)  

        ![Failing command](/journal/assets/synk-result-backend.png)

    - Repated same process  for fronted and this time found some ciritical issue present in this container.
     ![Failing command](/journal/assets/synk-front-end.png)
