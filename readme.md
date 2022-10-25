# ��Ƶ���ӻ��� / AudioVisualizer

�ֱ��� GDI+ �� Direct2D(SharpDX) ��ʵ������Ƶ���ӻ� \
Audio visualization on GDI+ and Direct2D (SharpDX) respectively

�����ѧ��: ���ʵ����Ƶ���ӻ�, ���ʹ�� SharpDX ���� 2D ��ͼ \
You can learn: how to implement audio visualization, how to use SharpDX for 2D drawing

![preview](res/preview1.png)

## ��Ҫ�߼� / Main logic

### ��Ƶ���ӻ� / Audio visualization

- ÿһ֡�Ծ����ݺ������ݽ��� "����", ֵ������������Ϊ��ֵ, ���Ǹ���Ϊ��ֵ���м�ֵ, Ҳ����˵, ÿһ��ˢ��, ����ֻ�� "�ƶ�" һ������ \
  Each frame do lerp operation between the old data and the new data, the value is not updated to the new value immediately, but is updated to the intermediate value of the two values, that is, each refresh, the data will only "move" a certain percentage
- �Ӹ�������, �ڸ�ס��Ƶ���Ƶ, ��Ҫչʾ�м�Ƶ�� \
  Add a window function to cover the low frequency and high frequency, mainly showing the middle frequency
- ����Ƶ�����ֵȡ����, ���������� "����" ���Ӿ�Ч�� \
  Take out the value of the low-frequency area and use it separately for the visual effect of "bass"

### WinForm

- ʹ�� WinForm �� Timer ʵ���ڵ��̵߳Ķ�ʱƵ�����ݻ�ȡ�Լ�����ˢ�� \
  Using WinForm's Timer to achieve timed spectrum data acquisition and interface refresh in a single thread

### GDI+

- ʹ�� BufferedGraphics ʹ����ʱ�������� \
  Use BufferedGraphics to draw without flickering

## Enjoy

����ע�ͺ�����, ����, ѧ����ѽ~ \
The code comments are very perfect, so let's just learn it~

![code](res/code.png)