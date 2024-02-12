# Unscented Kalman Filter

#### Process Model

* The UKF implementation was done using only orientation(gyroscope) in the state vector as the control input: q = [q0, q1, q2, q3]^T
* Initialize P (Covariance matrix) as size of 3x3. Similarly, R and Q. R is measurement noise and Q is process noise.
* After Kalman filter predict step, new P and state vector q are obtained, which are the used for update step.
* Then Sigma Points are obtained by Cholesky decomposition of (P+Q).

#### Motion Model

* This step deals with updating P and getting new mean state q. Which then leads to obtaining new Sigma Points. This new sigma points are used to calculate multiple covariances, like Pzz, Pxz, and Pvv.
* The next step involves computing K (Kalman Gain) = Pxz Pvv-1 and I (Innovation term) = Accelerometer reading – Mean of Sigma Points
* These are used to calculate the P and q for the next stage.



### Results

![](https://github.com/Iron-Stark/Orientation-Tracking-Using-Unscented-Kalman-Filter/blob/master/results/IMU_1.png)

![](https://github.com/Iron-Stark/Orientation-Tracking-Using-Unscented-Kalman-Filter/blob/master/results/IMU_2.png)

![](https://github.com/Iron-Stark/Orientation-Tracking-Using-Unscented-Kalman-Filter/blob/master/results/IMU_3.png)

### Instructions

Run python3 estimate_rot.py to visualize the results.



