task :build , 'keymap'
task :build do | t, args |
  next if args['keymap'].nil?
  sh "docker run --rm -e keyboard=helix -e subject= -e keymap=#{args['keymap']} -v $(pwd):/qmk qmk"
end

task :write , 'keymap'
task :write do | t,args |
  next if args['keymap'].nil?
  sh "sudo avrdude -p atmega32u4 -c avr109 -P /dev/tty.usbmodem* -U flash:w:.build/helix_rev2_#{args['keymap']}.hex"
end
