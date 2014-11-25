Configure the Solver for zhuzhuNet
========================
### 1. Solver Parameters
1. base_lr
   * i.e. base_lr : 0.01 
       * begin training at a learning rate of 0.01 = 1e-2
2. lr_policy
   * fixed: always return base_lr.
   * step: return base_lr * gamma ^ (floor(iter / step))
   * exp: return base_lr * gamma ^ iter
   * inv: return base_lr * (1 + gamma * iter) ^ (- power)
3. gamma
   * drop the learning rate by a factor of gamma
      * i.e. Multiply it by a factor of gamma = 0.1)
4. stepsize (drop the learning rate every 100K iterations)
   * i.e. stepsize:100000
5. max_iter: 350000 
   * max_iter: 350000 (train for 350K iterations total)
6. momentum
  * $$ V_{t+1} = \mu V_t - \alpha \nabla L(W_t) $$ 
7. 
Wt+1=Wt+Vt+1
### 1. Solver Type
1. Fixed
   * Always return base_lr
// policies are as follows:
//    - fixed: always return base_lr.
//    - step: return base_lr * gamma ^ (floor(iter / step))
//    - exp: return base_lr * gamma ^ iter
//    - inv: return base_lr * (1 + gamma * iter) ^ (- power)
