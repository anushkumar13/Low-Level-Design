# Elevator Design Requirements (Simplified)

## 1. Elevators and Floors

* The building will have multiple elevator cars and multiple floors to serve.

## 2. Building Limits

* Maximum of 15 floors.
* Up to 3 elevators can operate in the building.

## 3. Elevator Movement

* Elevators can:

  * Move up
  * Move down
  * Stay idle (not moving)

## 4. Elevator Door Operation

* Elevator doors can open only when the elevator is in an idle state (not moving).

## 5. Floor Access

* Each elevator car is capable of stopping at every floor in the building.

## 6. Outside Panel

* Each floor will have an outside panel:

  * With buttons to call an elevator.
  * Indicate direction preference: Up or Down.

## 7. Inside Panel

* Each elevator will have a control panel inside:

  * Buttons for all floors.
  * Buttons to open and close the elevator doors.

## 8. Displays

* Each elevator will have displays:

  * Outside: shows current floor and direction.
  * Inside: shows current floor, direction, and capacity status.

## 9. Floor Panels and Displays

* Each floor will have its own:

  * Panel to call elevators.
  * Display to show elevator status and movement.

## 10. Passenger Directions

* Multiple passengers can use the same elevator at once.
* Passengers may go to different floors or directions within the same ride.

## 11. Elevator Control

* The system will:

  * Manage elevator movement.
  * Operate doors.
  * Monitor the status of each elevator.

## 12. Smart Dispatch

* When a passenger calls an elevator:

  * The system selects the most suitable elevator.
  * Decision is based on current elevator positions and directions.

## 13. Capacity

* Each elevator can carry:

  * Maximum 8 people, or
  * Total weight of up to 680 kilograms.

---

## System Design References

###  Use Case Diagram  
You can view the use case diagram at the following link:  
[Click here to open Use Case Diagram](https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&dark=1#R%3Cmxfile%3E%3Cdiagram%20name%3D%22Page-1%22%20id%3D%22B4gbD_VANNIKZfwYgHy_%22%3E7Ztbb6M4FMc%2FTR53xc1cHtu03X2YkartSLv76AQnsWpwBpwm2U%2B%2FdjA3mzaECTjVTFWp%2BGAM%2FP079vExnbnz5PBHBrebrzRGZOZY8WHmPswcxwG%2By%2F8Iy7Gw2L4PCss6w7G01YYX%2FB%2BSRktadzhGeasio5QwvG0blzRN0ZK1bDDL6L5dbUVJ%2B65buEaa4WUJiW79G8dsI62OZdUn%2FkR4vSlv7ZdnEljWloZ8A2O6b5jcx5k7zyhlxVFymCMi5CuFKa57euds9WQZSlmfC5J0k7x9S7%2FH8e7r6zN%2BIt8e499kK2%2BQ7OQby4dlx1KCjO7SGIlG7Jl7v99ghl62cCnO7nmvc9uGJUSels2hjKHDu89pV2%2FPwUE0QSw78iolNa4UTDLjebK8rzsg8KVt09DeL5WGstPXVdu1LPxAKnOBSo6m0jPMc5SuUabJxbt5Kw53CblbMppxUYQcmDP1BS4QeaY5ZpimvMqCMkaTRoU7gtfiBKPXlzVoq%2Br7Hap2iGqPJmqgibrNUJ6Ly9Kce%2F3p7dLTgLLYcaFSTWp%2BEz4OoEmodO22fsDS9bO7BAzH0i98Vz%2B6Y7cnoBOBloBhqAtYDatNAaOxBIw0AbkLiqtQgrI1SpdHs4KFiscGHcR5HYIFYwlWukBDsZjyEY4Tt0WcLks0z%2BdiQnMBX4a%2B71DOjIoIHEVEx7Tb2vqUuyKFijchmDJPeJFx6vTZN6FvqMItF7OlYxG8Mqtc4CkzhHnlXE25TkctnNigdB5oSxcA49J5mnSVd%2FJVhPBWRNAbZIaVAwp0kXnlgD5J4HwL2XIjomULkjU166fKvBqa91Nfk6wKgQtPrSM6oSWBZiOTwOnhrmGHgqOFcra%2BmNAVSuM7kRHgpQWhy1euRQzzTbWy5eefsLjtg1WUZDaCzz8tAev1sFXJiWItjXBWzKZY5WIsQwQy%2FNZuq0st2dwzxSmrO8aPlCkIKILndJctkbyqmStQGlJ9BKg9xyCPkJnWEBdYsFlV24oKuda9lQo%2FsCTvkbkYp8fRAbN%2FxPHvQJb%2BLdvjxw%2BHRrWH44WU8Mc%2F9dDZIHwSnICCU6DmAvriBJSUThUqncHparDoIeTksISR08CFl33%2FQ2RE4RllmL87nzfLu3IdiuYsKyoNRXtO6JeGusFT6dgsqU1ekUyZkCj68mxsNQnBrkKwbVlDEQbnWhqbYT3f04fhBqi%2BRvH72NaggSZm9jnEOsdGa6qxMepJYDAdgEra0HcH8uep%2BVu1obHx07NlE%2BBnD4LPBHplP98Qe1WKukRGDeJ6j31eO3XrTzz0lagbZK8xDl5CXzUMjs%2BffXv8qblXeyh%2Ffps%2FoMahY%2FOnrzVejjlDiUbhrW7%2B2Za6mWB8%2B8%2FVM2wfOXVKU9QvYhnmtnbLbV3l5%2BJI%2FYqe7VzNsUFHB4Pr%2BHo1ZpQrvKFxtq2mMPyJfV1PX5rAsj8%2FZ7kIjXLhXYkL9fuFaGouLlt%2BDeWia%2BC5ePT6OOgYOw1QZrPPgumeT4yOSGakRMe2rRLVe8iyFDYnzw14lwXIPzOc4FPAGSgJU9sdmno9j%2FnYbHYl6n2YiCCXsFPvtksWTpdkJze%2F5Kl1q6IsKYDz6FjYc5bRVzSnRETfJeorvvBTTFCG2wStWEcUnuA4Fi3f51u4xOn6y6nag1db%2FpK9LkyUX74iJ%2Bfa8AsRb%2BFe7n3wZwP3%2FJe%2FzFzQD%2FizznnZrsv8V1TP2Jym%2FPEhPlGNYM72YsNZuCeDDC5ObyocYoIdebe95Io6Pj4Kgc6%2FmpW62nLBc35h9PkwUr8mCmzTGOmfxPzC6OYx8sE7i0JjGF05eTE0Uir2WqIobAdqnmV6L7D89Oz8ZqDJMEvlKlA%2F8en9vYQSZWk75WMHWVfOWlTbeFHktZiUZA3ctf6x5cTYyH6KlYFtKUuDwd%2F4aDlhMPWqVf%2Fszdwgetto9s0BG06pKMm%2BwRmVSP1sQ905GkwmL9b%2FcVdUr%2F9z0X38Hw%3D%3D%3C%2Fdiagram%3E%3C%2Fmxfile%3E)

---

###  Classes  
You can view the classes here:  
[Click here to open Classes](https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&page-id=DOsgbTSjDVrFLCh3Mw3s&dark=1#R%3Cmxfile%3E%3Cdiagram%20name%3D%22Page-1%22%20id%3D%22B4gbD_VANNIKZfwYgHy_%22%3E7Ztbb6M4FMc%2FTR53xc1cHtu03X2YkartSLv76AQnsWpwBpwm2U%2B%2FdjA3mzaECTjVTFWp%2BGAM%2FP079vExnbnz5PBHBrebrzRGZOZY8WHmPswcxwG%2By%2F8Iy7Gw2L4PCss6w7G01YYX%2FB%2BSRktadzhGeasio5QwvG0blzRN0ZK1bDDL6L5dbUVJ%2B65buEaa4WUJiW79G8dsI62OZdUn%2FkR4vSlv7ZdnEljWloZ8A2O6b5jcx5k7zyhlxVFymCMi5CuFKa57euds9WQZSlmfC5J0k7x9S7%2FH8e7r6zN%2BIt8e499kK2%2BQ7OQby4dlx1KCjO7SGIlG7Jl7v99ghl62cCnO7nmvc9uGJUSels2hjKHDu89pV2%2FPwUE0QSw78iolNa4UTDLjebK8rzsg8KVt09DeL5WGstPXVdu1LPxAKnOBSo6m0jPMc5SuUabJxbt5Kw53CblbMppxUYQcmDP1BS4QeaY5ZpimvMqCMkaTRoU7gtfiBKPXlzVoq%2Br7Hap2iGqPJmqgibrNUJ6Ly9Kce%2F3p7dLTgLLYcaFSTWp%2BEz4OoEmodO22fsDS9bO7BAzH0i98Vz%2B6Y7cnoBOBloBhqAtYDatNAaOxBIw0AbkLiqtQgrI1SpdHs4KFiscGHcR5HYIFYwlWukBDsZjyEY4Tt0WcLks0z%2BdiQnMBX4a%2B71DOjIoIHEVEx7Tb2vqUuyKFijchmDJPeJFx6vTZN6FvqMItF7OlYxG8Mqtc4CkzhHnlXE25TkctnNigdB5oSxcA49J5mnSVd%2FJVhPBWRNAbZIaVAwp0kXnlgD5J4HwL2XIjomULkjU166fKvBqa91Nfk6wKgQtPrSM6oSWBZiOTwOnhrmGHgqOFcra%2BmNAVSuM7kRHgpQWhy1euRQzzTbWy5eefsLjtg1WUZDaCzz8tAev1sFXJiWItjXBWzKZY5WIsQwQy%2FNZuq0st2dwzxSmrO8aPlCkIKILndJctkbyqmStQGlJ9BKg9xyCPkJnWEBdYsFlV24oKuda9lQo%2FsCTvkbkYp8fRAbN%2FxPHvQJb%2BLdvjxw%2BHRrWH44WU8Mc%2F9dDZIHwSnICCU6DmAvriBJSUThUqncHparDoIeTksISR08CFl33%2FQ2RE4RllmL87nzfLu3IdiuYsKyoNRXtO6JeGusFT6dgsqU1ekUyZkCj68mxsNQnBrkKwbVlDEQbnWhqbYT3f04fhBqi%2BRvH72NaggSZm9jnEOsdGa6qxMepJYDAdgEra0HcH8uep%2BVu1obHx07NlE%2BBnD4LPBHplP98Qe1WKukRGDeJ6j31eO3XrTzz0lagbZK8xDl5CXzUMjs%2BffXv8qblXeyh%2Ffps%2FoMahY%2FOnrzVejjlDiUbhrW7%2B2Za6mWB8%2B8%2FVM2wfOXVKU9QvYhnmtnbLbV3l5%2BJI%2FYqe7VzNsUFHB4Pr%2BHo1ZpQrvKFxtq2mMPyJfV1PX5rAsj8%2FZ7kIjXLhXYkL9fuFaGouLlt%2BDeWia%2BC5ePT6OOgYOw1QZrPPgumeT4yOSGakRMe2rRLVe8iyFDYnzw14lwXIPzOc4FPAGSgJU9sdmno9j%2FnYbHYl6n2YiCCXsFPvtksWTpdkJze%2F5Kl1q6IsKYDz6FjYc5bRVzSnRETfJeorvvBTTFCG2wStWEcUnuA4Fi3f51u4xOn6y6nag1db%2FpK9LkyUX74iJ%2Bfa8AsRb%2BFe7n3wZwP3%2FJe%2FzFzQD%2FizznnZrsv8V1TP2Jym%2FPEhPlGNYM72YsNZuCeDDC5ObyocYoIdebe95Io6Pj4Kgc6%2FmpW62nLBc35h9PkwUr8mCmzTGOmfxPzC6OYx8sE7i0JjGF05eTE0Uir2WqIobAdqnmV6L7D89Oz8ZqDJMEvlKlA%2F8en9vYQSZWk75WMHWVfOWlTbeFHktZiUZA3ctf6x5cTYyH6KlYFtKUuDwd%2F4aDlhMPWqVf%2Fszdwgetto9s0BG06pKMm%2BwRmVSP1sQ905GkwmL9b%2FcVdUr%2F9z0X38Hw%3D%3D%3C%2Fdiagram%3E%3Cdiagram%20id%3D%22DOsgbTSjDVrFLCh3Mw3s%22%20name%3D%22Page-2%22%3E7VxZc%2BI4EP41VE0emPKBOR5jnDmqdqtSm5nKzqPACqgiW15ZBNhfvy1ZPjFHNuAYZ3ix1ZbVUh%2BfuiWZnj0NNl85ipZ%2FMh%2FTnmX4m57t9SzLHpgjuEjKNqHAz0goC078hGbmhAfyL9bEtNqK%2BDguVRSMUUGiMnHOwhDPRYmGOGfrcrUnRstcI7TAO4SHOaK71Efii6WmWoaRP%2FiGyWKZsh6mTwKU1taEeIl8ti6Q7LuePeWMieQu2EwxleJLBZO892XP06xnHIfilBceH%2Be%2Fvpqj7z8W%2FPvdkvycrSa3fd3KC6IrPeKeNaTQnhvJLoutFsTwn5XspxsgviBhz741ok1W7AsWAWmgSAJvRB9RspC15tA3zIGatwB3C31VfGYFAgqgHZfWlQw0iwVHoGI5TP2s%2FF65FM7iqMAG5DKrYV0zxBmaPy84W4V%2Bf84og97fSqvjKIxTYbvK4rJnVOq%2F7yP%2B%2FIkvZp%2Bgf9OeshB1uUmu8onlOEmheHNzUysfdyUECw91H2hRlbbkckypG6VtmsXm64bMuI95Xz%2B4jRmVRnNAaa8xDoqfRGYdu03GAolVnAhyBq7drdFFHMfxp5sjWjsjQxLfS5bYP8DUKrGzXjAXBCDvNnFaT3mzq13YS%2Fi5DGo9UYVfTwRwBZQhArh4Jtyul0TghwjNZYtrmAoyNrJtvNmLWGaGgzCFYBZgwbdQRb%2FgmOPkFT17jGwNpesCFA81bVlA4YmmIY3%2Bi6zpHB%2FhRkPkK%2BDSag9cfkOUfhSMgBBAfKEsxVsC5nPVhm2NyoY9Gb23YdvtMew7il%2BQYPzDGDfhELkSFroiTOzbSykPydzYzMyRKYIflvO1ONnIaZuTpUlNycsq4qQkxCoq4uw5SzmklKTcpknM6YVMVaoIuaqJgPg%2BVY2BbEm4%2BCE14%2FXNnPKHetGzc8pfWgySxBmYH5qpnhlQpmiG6T2LiTRNoPGkrhsxAGQlK8ftOZ6icDFloQzYiVIWRrFYA4hnI0tHQsIl5kScR%2BP2sKJxc1fjg3GNxseXUnhdvFBROA79W5mo5motuIZKQ7CvFYA3RPwt7z87Q0uXf0mVGp8Nw9YEb1Oo7W0LhXuQNIxL4rCiJV3B%2Fk4GXJE3dJet%2BBwfi4t29VKQu1Mj9pTGMUWCvJS7UacMzeGeqQggm00Hexw9bSLpvn6rmCFXGtq1n0G5IQFAisVOQ8o2smG%2FwVzqZuGrM5f3MoPxucxgp6GmzWCwYwZ3GwGKjw9Zw4yy%2BbNUXZguo5nDpPhFzbhKh%2FttJYQ%2Ba2NJi790TVXI7USVtq80CstIhHZo2EeNJ5ut32gpzuSIgk%2B1lOG43JBpGEajppICRJvi9nsUYtr9sP1J5qNJjqJXr7LEBeL4kUsJhDsjr6HgnUU41AmT7Ev9GijEeGGblzyLAszFlvT6uAmdUZpzymL8W5znzizbLjAcYEDrcL49qvo9cmz7AFtnEV1ZazDHdjkQsEbOTupp1qWepmnsD1%2FetlbdojU9uVj9QeKChjxoFRVAylCbASWnviRvn63Deu77wPIKXdoxqy49rnHpZnefdhPDd%2FNoj8QRRdvu%2B%2FPTCftOl9sTeM8NgTmSa8Jie9Lgr0%2Bx8ZKt04BIW3OTG%2FWSvQTO46yvBTHHThUxU3Q8hpjm4GKQ6bQIMiWQdB4v5XkerGELBvygit0aIfDCHfBXs7IMajqn%2BuvlIpxhe9w1nRu677KSU8PxTRZTVUDxojNujkypbhuNp3wdMuuQrho%2FX5J1pHLv0tCr6fhFI8kVl6BUOMKV3DbDPUCbabdDWbn6Lx2pyfhVrZE3zTSAebLRIB1mkg7M9NWDtKYzOXGmz75eOP9UP2rPVF9Fo9%2Fz%2FJk43ufzTt0ScJtm2%2BtT5xI8cc3483Vj07hyTNMc1pzaq181MJ1LYdO4Pdjkrgj1SbjoPjyplda4GB82fYoC69i4cqCj8X5kRtCV7dHqSkMLvuSZtMfFe4e%2FfMThKugd%2B%2Bpxf0rbUbSQqcDPqMG8w2PrpjZYiTy3%2Fxtq%2FhfUVE9iTCYnnsS43LdVRsegZv92ZEexpjGcaRBjuub4jlGOMazsLPYxxx9fzPGv598VTnR89nHiC7mm2pArqqXU6%2Fa%2BahZf7311Ef7lvK9F5x%2Bz4HwbCxx033lm6aKFyqNrljA6MMaAhQRUCuNqdEcCU4i9XByL1KY6uD9hWad%2Bq21WP7g6AT6gmP%2FrUvIlVv7vVfbdfw%3D%3D%3C%2Fdiagram%3E%3C%2Fmxfile%3E)


---

###  Class Diagram 
You can view the class diagram here:  
[Click here to open Class Diagram](https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&page-id=XvMySOtdrrc5NLSRfN-h&dark=1#R%3Cmxfile%3E%3Cdiagram%20name%3D%22Page-1%22%20id%3D%22B4gbD_VANNIKZfwYgHy_%22%3E7Ztbb6M4FMc%2FTR53xc1cHtu03X2YkartSLv76AQnsWpwBpwm2U%2B%2FdjA3mzaECTjVTFWp%2BGAM%2FP079vExnbnz5PBHBrebrzRGZOZY8WHmPswcxwG%2By%2F8Iy7Gw2L4PCss6w7G01YYX%2FB%2BSRktadzhGeasio5QwvG0blzRN0ZK1bDDL6L5dbUVJ%2B65buEaa4WUJiW79G8dsI62OZdUn%2FkR4vSlv7ZdnEljWloZ8A2O6b5jcx5k7zyhlxVFymCMi5CuFKa57euds9WQZSlmfC5J0k7x9S7%2FH8e7r6zN%2BIt8e499kK2%2BQ7OQby4dlx1KCjO7SGIlG7Jl7v99ghl62cCnO7nmvc9uGJUSels2hjKHDu89pV2%2FPwUE0QSw78iolNa4UTDLjebK8rzsg8KVt09DeL5WGstPXVdu1LPxAKnOBSo6m0jPMc5SuUabJxbt5Kw53CblbMppxUYQcmDP1BS4QeaY5ZpimvMqCMkaTRoU7gtfiBKPXlzVoq%2Br7Hap2iGqPJmqgibrNUJ6Ly9Kce%2F3p7dLTgLLYcaFSTWp%2BEz4OoEmodO22fsDS9bO7BAzH0i98Vz%2B6Y7cnoBOBloBhqAtYDatNAaOxBIw0AbkLiqtQgrI1SpdHs4KFiscGHcR5HYIFYwlWukBDsZjyEY4Tt0WcLks0z%2BdiQnMBX4a%2B71DOjIoIHEVEx7Tb2vqUuyKFijchmDJPeJFx6vTZN6FvqMItF7OlYxG8Mqtc4CkzhHnlXE25TkctnNigdB5oSxcA49J5mnSVd%2FJVhPBWRNAbZIaVAwp0kXnlgD5J4HwL2XIjomULkjU166fKvBqa91Nfk6wKgQtPrSM6oSWBZiOTwOnhrmGHgqOFcra%2BmNAVSuM7kRHgpQWhy1euRQzzTbWy5eefsLjtg1WUZDaCzz8tAev1sFXJiWItjXBWzKZY5WIsQwQy%2FNZuq0st2dwzxSmrO8aPlCkIKILndJctkbyqmStQGlJ9BKg9xyCPkJnWEBdYsFlV24oKuda9lQo%2FsCTvkbkYp8fRAbN%2FxPHvQJb%2BLdvjxw%2BHRrWH44WU8Mc%2F9dDZIHwSnICCU6DmAvriBJSUThUqncHparDoIeTksISR08CFl33%2FQ2RE4RllmL87nzfLu3IdiuYsKyoNRXtO6JeGusFT6dgsqU1ekUyZkCj68mxsNQnBrkKwbVlDEQbnWhqbYT3f04fhBqi%2BRvH72NaggSZm9jnEOsdGa6qxMepJYDAdgEra0HcH8uep%2BVu1obHx07NlE%2BBnD4LPBHplP98Qe1WKukRGDeJ6j31eO3XrTzz0lagbZK8xDl5CXzUMjs%2BffXv8qblXeyh%2Ffps%2FoMahY%2FOnrzVejjlDiUbhrW7%2B2Za6mWB8%2B8%2FVM2wfOXVKU9QvYhnmtnbLbV3l5%2BJI%2FYqe7VzNsUFHB4Pr%2BHo1ZpQrvKFxtq2mMPyJfV1PX5rAsj8%2FZ7kIjXLhXYkL9fuFaGouLlt%2BDeWia%2BC5ePT6OOgYOw1QZrPPgumeT4yOSGakRMe2rRLVe8iyFDYnzw14lwXIPzOc4FPAGSgJU9sdmno9j%2FnYbHYl6n2YiCCXsFPvtksWTpdkJze%2F5Kl1q6IsKYDz6FjYc5bRVzSnRETfJeorvvBTTFCG2wStWEcUnuA4Fi3f51u4xOn6y6nag1db%2FpK9LkyUX74iJ%2Bfa8AsRb%2BFe7n3wZwP3%2FJe%2FzFzQD%2FizznnZrsv8V1TP2Jym%2FPEhPlGNYM72YsNZuCeDDC5ObyocYoIdebe95Io6Pj4Kgc6%2FmpW62nLBc35h9PkwUr8mCmzTGOmfxPzC6OYx8sE7i0JjGF05eTE0Uir2WqIobAdqnmV6L7D89Oz8ZqDJMEvlKlA%2F8en9vYQSZWk75WMHWVfOWlTbeFHktZiUZA3ctf6x5cTYyH6KlYFtKUuDwd%2F4aDlhMPWqVf%2Fszdwgetto9s0BG06pKMm%2BwRmVSP1sQ905GkwmL9b%2FcVdUr%2F9z0X38Hw%3D%3D%3C%2Fdiagram%3E%3Cdiagram%20id%3D%22DOsgbTSjDVrFLCh3Mw3s%22%20name%3D%22Page-2%22%3E7VxZc6M4EP41rpo8eIojYPsxmGRmqnarUpuZys6jDIqtipBYIcf2%2FvqVhDiNj2xsgkmejBpQS3183S0JD%2BxptP7GQLz4k4YQDywjXA9sf2BZluPa4kdSNinFdF0npcwZCjWtIDygf6EmGpq6RCFMKg9ySjFHcZUYUEJgwCs0wBhdVR97orjKNQZzuEV4CADepj6ikC801TKM4sZ3iOaLjLWb3YlA9rQmJAsQ0lWJZN8O7CmjlKdX0XoKsRRfJpj0vbsdd%2FORMUj4MS88Pga%2Fv5mjHz%2Fn7MftAv2aLSc3Q93LC8BLPeOB5WLRnxfLIfONFoT7z1KO04sAmyMysG%2BMeJ03h5zGgnStSByu%2BRBgNJdPBWJskAlq0YO4mutfxWdWIoBI9OPhppYBZglnQKhYTlPfq75XbZFZEpfYCLnMGlg3THEGguc5o0sSDgOKqRj9jbQ6BkiSCdtTFpffw1L%2FwxCw5y9sPvsixjcdKAtRP1fpr7xjOU7aKF9cXTXKx1tyTsm%2B4QtaXKctmJxT5kZZn2a5%2B6YpUxZCNtQ3bhKKpdHsUdprjAPDJ55bx3aXCQd8maSCnAnX7tfsYgaT5MvVAa2dkCFK7iVLGO5halXYWS%2BQcSQg7yZ1Wl95s6dd2E%2F5eVQ89YQVfj0hgStCGTwSP74pLlcLxOFDDALZ40qEgpyN7BuudyKWmeOgCCGQRpCzjXhEv%2BCY4%2FQVHT1GtobSVQmKXU1blFB4omlAo%2F8877rAR3GhIfIVcGl1By6%2FA4w%2FCkaIFIDfYZrhLRLmc9GGbY2qhj0Zvbdh290x7FsMXwCn7MMYN2Iic0WUeJyk9u1nlIc0NrYTOXJFsP1yvhQnGzldc7KsqKl4WU2cGBGosiJGn%2FOSQ0pJym2a5pw%2BoeqhmpDrmohQGGLVmZAtIvOfUjP%2B0Cwof6gXfbug%2FKXFIEmMCvMDMzUyQ7QxmEF8TxMkTVPQWPqsF1MByEpWjjdwfEVhfEqJTNiRUhYECV8JEM9nls0EkQVkiJ9G47Zb07i5rfHrcYPGx%2BdSeFO%2BUFM4JOGNLFQLtZZcQ5UhMNQKgGvE%2F5bXXx3X0u3fUqXGV8OwNcFfl572N6XGvZC0mJfEYUVLhwLDrQq4Jm8xXLpkATyUF23rpSR3p0HsGY1BDDh6qQ6jSRmawz1VGUAeTa93OHrWRTp8%2FVa5Qq51tG0%2F19WOuABSyLc6UraRT%2FsN5tIUhS%2FOXN7LDManMoOtjto2g%2BstM7hdc6H4ZJ81zDANnqXqSLaMZrpp805FXKXD3bZCxJi1sWTN3%2FpJ1SjsRLU2rzQKy0iFtm%2FaB40nj9ZvtBRnckDBx1qKO652ZBqG0aqpZADRpbz9HhCI%2B5%2B2P8l6NK1R9OpVXriIPH7kYSTSnZHfUvJOY0h0wSTH0rwGKnI80uUlz7IAC7Gloz5sQieUZoBpAj%2FFeerKsusCgxEUaE2CzUHV75Bj1yfYOYvoy1qDObariYA1crZKT7Op9DRNY3f68ra16g6t6cnF6g%2BSF7TkQcu4BFKG2gyoOPU5eYd0RZq57wLLC3Rpx6y79LjBpdvdfdouDN%2FNo32UxBhs%2Bu%2FPT0fsO51vT%2BA9NwQCINeE%2BeaoyV%2BeYpMFXWUJkbbmNjfqJXsJnIdZXwpijp06YmboeAgxzeuzQabTIciUQNJ7vJTneaCGLTHhB9Xs1wwFL9gDfzVry6Cmc6y%2Fni%2FDcbvjrlls6L%2FLSk4t5zd5TlUDxbNG3AKZMt22mk%2BFOmXWKV09fz4n61jV3pWp18vxs2aSSyZBqXSEK71sh3sE1tN%2Bp7Jy9V86Upv5q1ojb5tpJOJkq0m6iCQ9iPT1g7SmMzky0udfL5w%2B1I%2B6E%2BrraPQZ50%2FE8b6IO01LwF2KtpenzoXwxBVlz5eNTePaMU3TbTi117xqYDrnwqZxd7DJWyIcIjLvPzypldaknB%2B2fYoC6ty4dqCj9XHkRtCX7dH6SkMHvuSZdMfFB%2Fu%2FfIRkGQ0OffW4u6TtKVrIUuBX3GLd4dNVWxusSJ7b%2F4Sa%2FwU19ZMYk8mRJzHO922V0TOo2b0d2VOsaQ1nWsSYvjm%2BY1RzDCs%2Fi33I8cdnc%2FzL%2BXeFIx2ffpz8Qq6ptuSKain1sr2vXsU3e19Thn8%2B7%2BvQ%2Bcc8Od8kHEb9d55Ztmih6uiGJYwezDGiBAmVinm1uiMBsci9PJjwzKZ6uD9hWcd%2Bq23WP7g6Aj5Es%2FjXpfRLrOLfq%2Bzb%2FwA%3D%3C%2Fdiagram%3E%3Cdiagram%20id%3D%22XvMySOtdrrc5NLSRfN-h%22%20name%3D%22Page-3%22%3E7Vxbd5s4EP41Pqd9cA7iaj%2FGJtl2t91N4nab7UuPDIrNGiMq5NjOr18JxE3GlziYEHfzEjRgXWa%2BGX0jCTracL76jcBw%2Bhm7yO%2BoirvqaHZHVUHP1Nk%2FLlkLiQpAIpkQzxWyXDDynpAQKkK68FwUlR6kGPvUC8tCBwcBcmhJBgnBy%2FJjD9gvtxrCCdoQjBzob0q%2FeS6dpsNQlPzGB%2BRNpmnTZnpnDtOnhSCaQhcvCyLtqqMNCcY0uZqvhsjn6ksVk%2FzuesvdrGcEBfSQHyy7HvwAPlsz7Y%2Fr7uqWPP01XnVFLY%2FQX4gRd1TTZ%2FUNQt5luhaKMH8ueD8Hc0gmXtDRLpVwlRW7FIdMpMciila0C31vwp9yWN8QYdK8BnY1Ef%2FjdsYFAZyzegZ%2BVUmB44gSyEzMhynulX9XLgXjKCw0w%2FQyrmi6Yohj6MwmBC8Ct%2BtgH7PeX3LUERhEqbIHMeKyez63f9eFZPaOTMbvWP%2BGnRgh8b%2F3yX9%2BRzWMpFC8eP%2B%2BUj%2BDBaU42NV9Jgtl2ZTwMaVulNYJitVXDRkTF5GuuHEZYZ%2BDZofRngMOHz3QDB2bVUYU0kWUKHLMXPu8RhcSFEXv3u%2BxWo0NetENbxK5OxpVS82pj4hQj4W8y8Rp7dibB8KF7aS9AWZPPfhx%2FHrwWFxhxqBz9s8G7HI59SgahdDhNS7ZVJA1w%2BtGq60RC2RxkE0hCM8RJWv2iPhBTxehU8weutFLystCKDbFM9NCFO4LGRTRf5JVncdHdiFC5DPCpdqecPkB%2Bv6vEiMYBaDXPk7jrcfg86aBnZEEAWyz%2F9rA1toD7CsfPUKKyS8Dbo8w5urhYECDBN92Khklc2MzM0dmCLJbz2%2FFyYDSa5uX6RVeJqnT9wIUsyKCZ1nKwbXE9TZMOKcd4PghScmyJeae6%2FpxZUy3XjD5wi1jd0Eu%2BRT%2F0NZyyZ3QAhcRzOAHx3HPFFb24Rj5NzjyODSZjCTPDkLMAnKsKmPQMexYQugQB5ywe7GxEIzokgXxbGTpSLxgiohH67G42ZcMrm0aXO9VGLx3Insb%2B%2B2NAveS56m5VQueEWchyBX6RyuP3vPrC8NURfkfblHlQlE0IbBXhaftdaFwwxTNhsXDcCxLuoLcjQRYUjfrLl4QB%2B2jRZtmKajdqNB6KiPIh9R7LHejyhaihRscE4DU6oa1xc3TKpLui18VE2Spog346Gq5IsriKKIbFcXQyIZ9PFrMc0DLa6EAgLpgsFlTwziwnoWDsY%2BdGTdakC6fATMpXsczbWy97SgJWF8FTNLiP%2BLJuJAjJC6tnwkHVUmUtWO4%2B2GTTdIvxEhf3WPYgyGigHJNljyF1AeR2cPocWwPxrdo4jyB2dP6A7pt07LdYOH5LmMO50%2FUH3gGKlaqkmzUGvgeIzWW3RBFRyI1Ep1IM6XG%2B3F2qYJuSP4MGkwV7r5ffdG%2Bav%2FC365GC3R5%2B3X%2B97pNHp7CbLSOKJqfv5%2BP04gWO1lFfDuDMc5x4DGTsnE1uTgdsQDm0AFLBFNMncEq9Ubw6B8aPIByquhRtU69nUK6HmR4cL9MuUEl5pjTSlU%2FkEjqLO0uUMmcPFZTybh0knSjLt4IDA2ULNxTjs0tDE256JvVcKmfO%2F771UAD89t3%2B3ftezQi%2Fe63od%2FGmeUGBqi48XemE0tMIJNlbYnB8aXfpkkcDlEg1th5X6q3zaMQBtV6bMcueVGBudqSXu%2BHUI3adHwcof%2FVWXeG0XaFoTliwTpw1ntNv0WPbR9g6xBxNjmnIi0z9tUK2li1WwFADbQxQM4X51YZTP%2F8RC%2BBjX5eWQ9togb8eMMvQgsacqBFWIhRSnx8pOTTp2zbxcuguvVtsfINerR8qqNfsf14skWkSn%2BuJw1M9gIOTAPzXadOvucEOju3m7bsQexLHA%2FNEQ%2FdwCzvVWwPkI3knLq0V9E7djvL6O2pqL50s1JlVSeL2ofBdq03AKN%2FoSv9%2FK9kQat39M6muYVy1I%2BF25Girz5OwA%2F%2Fo2t7jrW%2B%2BjlpE7%2FI9k7Onl7wlnaemjzBbJ%2BmJDYuafika8sUUlReVWn0%2BJzrRaEP1%2BkJvqTQTNNhzJNLQ5ep80mXPhaER8nCAd3kspnW53A1hPzwGl0fhPO358B8oY47UpM7NfFyVtONzhlrb3Q7is0k57ABpUmJh1a1klCVeGTvpr0k86ic6duSeWREb0%2Fm0SnmHXkacvrMo%2BKU1Hbq1Az7VGQ4WXXxzY2atvBNhgs%2BeWaPiRPGOwiz3GVBkXMIJ1Uey2b7i%2Fsf4%2Fvp%2FV%2F2aLX8qN39blzP2sRmJZ51pky2QPH4gEdx8bxGyNraNQW%2BmSnJlFYd1F6Da2Fd8%2Funx%2BHNt4WJJ7O%2FoRl9Jq06ULWZHZypwz4c8M7e6d6nes2XqZzzTkmiKV6mqaZAc6PEnTXPtxD2N%2F1mA6ZuHnqITD9VxHwFDp%2FycXChqJ0SJTfzQ2XbzpFlCYCSvAGRpgAXRs%2FqPPd9lxedSivz%2Fl3TUZt4vy69%2F2SYx%2FJ%2B09hTU33rzJXKfYU9hwJyFbMMXT153eoQ6JZhuxu09QF0V3bTJoBafa0MK%2Fn87OHHMK3qfPEEAAX%2B%2FePdhET9SA8nox%2BrO%2Fz0o01kVF6rPVMq2vwuyE2%2BKl91mKVNexFvz5xT5oJLTGZvnPXJnygA4NBvFABgvJz2VcamtizdtunQyK7d7OIMuf1lzYYonES8TP1oCgf21FTX0q0uv20N6l26rcT4AR%2FiaBPGGakEoITyC8PY94r2K2Qw27lOM%2FDvSaDtG8fC35IDsya%2F8lMX%2Fi1TngKacIDnfZnk1R2Af7RC7UseYOnNecCu49It8gD5EyZAPTaH7xn7aqrJASxLbkh9Ef5ZMf%2BmavJ4%2Fm1a7eo%2F%3C%2Fdiagram%3E%3C%2Fmxfile%3E)

---


###  Source Code  
You can download the implementation code from the following link:  
[Click Here for the Drive link](https://drive.google.com/file/d/1VZGZ86PgOhHshtfZYMT8bCj5-mvSnvOe/view?usp=drive_link)

---

##  What I Learned from Designing the Elevator System

When I started designing the Elevator System, I honestly thought — kitna complicated ho sakta hai, right? But bhai, jaise-jaise maine use cases and real-world flows sochne start kiye, I realized this is not just about “moving up and down”.

---

### 🔹 Mapping the Real World into Code

For the first time, I had to think — *what does an elevator system actually consist of*?  
So I broke it down into elevators, floors, buttons, panels, displays, and passengers.  
And suddenly, I had so many moving parts to model — both in my mind and in my code.

---

### 🔹 Elevators are Smarter Than We Think

I realized elevators don’t just move up and down blindly — they respond to passengers, directions, idle state, and optimize movement.  
So I had to build a basic **dispatch algorithm** to assign elevators based on direction, current floor, and idle status.

---

### 🔹 State Management is Key

Elevators have multiple states — moving up, down, idle, doors open, doors closed — and managing those transitions cleanly was honestly the hardest part.  
I had to make sure ki koi bhi invalid action na ho jaise moving elevator ke doors khul jaayein 😅

---

### 🔹 Designing Panels and Controls

Each floor had an outside panel and each elevator had its own internal control panel.  
I learned how to keep this part **user-centric** — making sure floors can call elevators, and elevators can take users to any floor safely.

---

### 🔹 Handling Multiple Passengers

Ek elevator mein multiple passengers ho sakte hain with different destinations.  
So I had to design it in a way where one trip can handle multiple requests — that means queues, floor request management, and smart stopping logic.

---

### 🔹 Keeping It Scalable and Clean

Even though the building only had 15 floors and 3 elevators, I wanted to write code that could scale.  
I focused on building clean classes with responsibilities clearly defined — like Elevator, Floor, Panel, and ElevatorController.

---

### 🔹 Real-Time Display Logic

The displays inside and outside the elevator needed to show current floor, direction, and capacity.  
This taught me how real-time feedback in systems is crucial for users and must be always synced with elevator state.

---

### 🔹 Putting It All Together

I learned how to bring all the small pieces together into one **working, controlled system**.  
The ElevatorController was like the brain — tracking elevator status, handling floor requests, and keeping things moving safely.

---

###  Final Thoughts

Honestly, this project made me think more deeply about system coordination, movement control, and state transitions.  
It wasn’t just about classes and code — it was about designing something that actually feels real and works like you'd expect it to.

Now I feel much more confident tackling design problems where multiple components interact in real-time.  
Still learning every day — but this gave me a big confidence boost 🚀

---