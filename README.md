Audite - a portable mp3 player in Ruby
======================================

Audite is a portable ruby library for playing mp3 files built on
libmp123 and portaudio.

## Features

* Nonblocking playback using native threads
* Realtime seeking
* Realtime events
* Progress information
* Simple level meter

## Usage

Audite ships an example player:

```
audite test.mp3
```

## API Example

```
require 'audite'

player = Audite.new

player.events.on(:complete) do
  exit
end

player.events.on(:level) do |level|
  puts level
end

player.events.on(:position_change) do |pos|
  puts pos
end

player.load('test.mp3')
player.start_stream
player.forward(20) 

```

## OSX Install

```
brew install portaudio
brew install mpg123

gem install audite
```


## Debian / Ubuntu Install
```
apt-get install portaudio19-dev libmpg123
gem install audite
```
