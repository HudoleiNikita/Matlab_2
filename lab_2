%% Read and listen
[bass, fs] = audioread('bass.mp3');
[guitar, fs] = audioread('guitars.mp3');
[synths, fs] = audioread('synths.mp3');
[drums, fs] = audioread('drums.mp3');
t_melody = length(bass) / fs;
%% Melody Matrix
melodyMatrix = [bass guitar synths drums];
tmpVector = ones(4, 1);
melody = melodyMatrix * tmpVector;
sound(melody, fs);
%% Minus one
melody1 = melody - guitar;
sound(melody1, fs);
%% Signal distortion
t_melody2 = t_melody / 2;
N = length(bass);
timearray = (0: N -1 ) / fs;
volumeMod = sin(2 * pi * timearray/ t_melody2);
volumeMod_tr = volumeMod';
melody2 = volumeMod_tr .* melody;
melody_square = volumeMod_tr.^2 .* 2 - 1;
sound(melody_square .* melody, fs);
%% Shorten melody
X = melodyMatrix'; 
tmp = X(1:1:length(X(:))/2);
halfMelodyMatrix = reshape(tmp, 4,length(tmp)/4);
halfMelody = sum(halfMelodyMatrix);
sound(halfMelody,fs);

%% 2-channel sound
