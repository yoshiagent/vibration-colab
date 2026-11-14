# 振動學：原課程 MATLAB 程式與 Simulink 模型的 Python 筆記本

「[振動學 Mechanical Vibration](https://yoshiagent.github.io/vibration/)」課程原本以 MATLAB 示範。這裡把原課程的 MATLAB 程式（`.m`，18 個）與 Simulink 模型（`nonsin.mdl`）改寫成 Python 筆記本，可以直接在 Google Colab 執行，不需要安裝任何軟體。

| 筆記本 | 內容（原課程的檔案） | 對照的網頁 | 開啟 |
|---|---|---|---|
| [弦波、相量與拍](notebooks/Sinusoids_Beating.ipynb) | phasor.m（相量與弦波動畫）、phasedif.m（相位差）、beatsound.m（拍的波形與聲音） | [網頁](https://yoshiagent.github.io/vibration/SIN.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/vibration-colab/blob/main/notebooks/Sinusoids_Beating.ipynb) |
| [單自由度自由與步階響應](notebooks/SDOF_Response.ipynb) | sys2ndfree.m（三種阻尼的自由響應）、order2step.m（步階響應與時域規格） | [網頁](https://yoshiagent.github.io/vibration/SD.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/vibration-colab/blob/main/notebooks/SDOF_Response.ipynb) |
| [簡諧激振](notebooks/Harmonic_Excitation.ipynb) | freqrespord2.m（二階頻率響應）、mck.m（質量阻尼彈簧）、seis.m（基座激振）、transm.m（力傳遞率）、rotorunb.m（旋轉不平衡） | [網頁](https://yoshiagent.github.io/vibration/HX.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/vibration-colab/blob/main/notebooks/Harmonic_Excitation.ipynb) |
| [傅立葉級數、頻譜與非弦波激振](notebooks/Fourier_Spectrum.ipynb) | FourierSq.m、FourierTriang.m（部分和）、freqspecsq.m、freqspec.m（頻譜）、ft01.m、ft02.m（傅立葉轉換）、nonsin.mdl（疊加原理） | [網頁](https://yoshiagent.github.io/vibration/FO.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/vibration-colab/blob/main/notebooks/Fourier_Spectrum.ipynb) |
| [二自由度系統與吸振器](notebooks/TwoDOF_Systems.ipynb) | dof2free.m（自由振動六個案例）、Dof2mkForced.m（強迫響應）、Dof2mkAbsorber.m（動態吸振器） | [網頁](https://yoshiagent.github.io/vibration/MD.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/vibration-colab/blob/main/notebooks/TwoDOF_Systems.ipynb) |

* 每段先列出原本的 MATLAB 程式，再給對應的 Python 版本（`tf`／`bode`／`lsim`／`step` 用 `scipy.signal`，`eig(K,M)` 用 `scipy.linalg.eigh`）。
* 每個結果都與理論值（閉式解、|G(jω)|、自然頻率）或 `solve_ivp` 數值積分交叉比對；網頁講義更正過的地方（編註）在筆記本裡也有數值驗證。
* 原課程的 `GUI_FourierSeries2.dll` 是編譯過的 MATLAB GUI，無法改寫；改用 Plotly 滑桿呈現傅立葉部分和。
* 每本都已實際執行（存有輸出與圖），只用 Colab 內建的 numpy、scipy、sympy 與 plotly。
