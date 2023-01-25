# TP4-Filtrage-Analogique


#Objectifs 
Appliquer un filtre réel pour supprimer les composantes indésirables d’un signal.
Améliorer la qualité de filtrage en augmentant l’ordre du filtre.

# Filtrage et diagramme de Bode
### 1)Définir le signal x(t) sur t = [0 5] avec Te = 0,0001 s.
```
    f1 = 500;
    f2 = 400;
    f3 = 50;
    Te = 0.0001;
    t = [0:Te:5-Te];
    x = sin(2*pi*f1*t)+sin(2*pi*f2*t)+sin(2*pi*f3*t);
```
### 2)Tracer le signal x(t) et sa transformé de Fourrier

<img width="1197" alt="Screenshot 2023-01-25 at 03 41 13" src="https://user-images.githubusercontent.com/87026851/214468777-faad1c4f-372d-47ec-917b-0be8d7f93a31.png">


```
subplot(2,2,1)
    plot(t,x);
    legend(" Signal x avec T =0.001");
    xlabel("t");
    ylabel("x(t)");

subplot(2,2,3)
    y = fft(x);
    plot(fshift,fftshift(abs(y)));
    legend(" Spectre du signal x avec T =0.001");
    xlabel("f");
    ylabel("A");


subplot(2,2,2)
    Te2 = 0.0005 ;
    fe2 = 1/Te2;
    t2 = [0:Te2:5];
    x2 = sin(2*pi*f1*t2)+sin(2*pi*f2*t2)+sin(2*pi*f3*t2);
    N2 = length(t2);
    fshift2 = (-N2/2:(N2/2)-1)*(fe2/N2);

    plot(t2,x2);
    legend(" Signal x avec T =0.0005");
    xlabel("t");
    ylabel("x(t)");

subplot(2,2,4)
    y2 = fft(x2);
    plot(fshift2,fftshift(abs(y2)));
    legend(" Spectre du signal x avec T =0.0005");
    xlabel("f");
    ylabel("A");
```
