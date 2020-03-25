# pcb_analysis
development of PCB simulation code


```
for i=1:length(stats.Centroid)
    ai = stats.Centroid(i, :);  % ai - indices of coordinate vectors for the position of the trap
    ai = round (ai);
    ac = [x_M(ai(1)), y_M(ai(2)), z_M(ai(3))]; % coordinates in physical space for the trap
    figure(1)
    plot3(ac(1), ac(2), ac(3), 'kx');
    
    figure (i+1);
    
    subplot(1, 3, 1);
    plot(x_M, B(:, ai(2), ai(3))*1e4);
    sgtitle(['position: x = ', num2str(ac(1)), 'm, y = ', num2str(ac(2)), ...
        'm, z = ', num2str(ac(3)), 'm']);
    xlabel ('x, m');
    ylabel ('B, G');
    
    subplot(1, 3, 2);
    plot(y_M, B(ai(1), :, ai(3))*1e4);
    xlabel ('y, m');
    ylabel ('B, G');
    
    subplot(1, 3, 3);
    plot(z_M, (squeeze(B(ai(1), ai(2), :)).')*1e4);
    xlabel ('z, m');
    ylabel ('B, G');
end
```
