## Running locally

* Install dependencies
   ```py
   pip install -r requirements.txt
   ```

* Download weights from model [here](https://drive.google.com/file/d/1CXWGf2hj_sJXIsSE4wfqUOqIv-EsYf7x/view?usp=sharing).

* You should now be able to spin up the API:

  ```py
  python3 api_upload.py -w PATH_TO_WEIGHTS
  ```

   `-w` is optional, and will by default refer respectively to `./efficientnetb0_512.hdf5`, so saving the weights in the same folder as `api_upload.py` without renaming the file will save you from specifying the path.
   
 You should now be able to send POST requests of your images as jpg or png file formats. The request must be sent to port 5000.

 A succesful response with code 201 could look like the following
 ```json
 {'audi': 1.5660635e-10, 'bmw': 5.7521644e-12, 'ford': 7.1362174e-12, 'jaguar': 7.3524025e-12, 'mercedes': 4.0594708e-11, 'mitsubishi': 3.221091e-14, 'nissan': 1.0, 'peugeot': 1.3644183e-11, 'porsche': 3.095818e-12, 'skoda': 1.0349395e-09, 'tesla': 2.1225747e-12, 'toyota': 1.0142925e-10, 'volkswagen': 4.066172e-12, 'volvo': 7.5269685e-10}
 ```

## Running on Docker

### Build image
```
 docker build -t apitest .
```

### Run image
```
 docker run -p 5000:5000 apitest:latest
```

Add `-d` to detach it from the terminal