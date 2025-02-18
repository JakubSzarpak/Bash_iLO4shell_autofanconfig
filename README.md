Only works with HPE iLO4 (2.73 - 2.77) with modified firmware that brings back fan control from 2.50 via SSH. 
Good solution for automatic custom PWM adjustment especially when Hard Drives forward their temperature in different range than 0-255 prefered by iLO4.


FAN:
Usage:

  info [t|h|a|g|p]
                - display information about the fan controller
                  or individual information.
  g             - configure the 'global' section of the fan controller
  g smsc|start|stop|status
          start - start the iLO fan controller
          stop - stop the iLO fan controller
          smsc - configure the SMSC for manual control
       ro|rw|nc - set the RO, RW, NC (no_commit) options
    (blank)     - shows current status
  t             - configure the 'temperature' section of the fan controller
  t N on|off|adj|hyst|caut|crit|access|opts|set|unset
             on - enable temperature sensor
            off - disable temperature sensor
            adj - set ADJUSTMENT/OFFSET
      set/unset - set or clear a fixed simulated temp (also 'fan t set/unset' for show/clear all)
           hyst - set hysteresis for sensor
           caut - set CAUTION threshold
           crit - set CRITICAL threshold
         access - set ACCESS method for sensor (should be followed by 5 BYTES)
           opts - set the OPTION field
  h             - configure the 'tacHometers' section of the fan controller
  h N on|off|min|hyst|access
             on - enable sensor N
            off - disable sensor N
            min - set MINIMUM tach threshold
           hyst - set hysteresis
 grp ocsd|show  - show grouping parameters with OCSD impacts
  p             - configure the PWM configuration
  p N on|off|min|max|hyst|blow|pctramp|zero|feton|bon|boff|status|lock X|unlock|tickler|fix|fet|access
             on - enable (toggle) specified PWM
            off - disable (toggle) specified PWM
            min - set MINIMUM speed
            max - set MAXIMUM speed
           blow - set BLOWOUT speed
            pct - set the PERCETNAGE blowout bits
           ramp - set the RAMP register
           zero - set the force ZEROP bit on/off
          feton - set the FET 'for off' bit on/off
            bon - set BLOWOUT on
           boff - set BLOWOUT off
         status - set STATUS register
           lock - set LOCK speed and set LOCK bit
         unlock - clear the LOCK bit
        tickler - set TICKLER bit on/off - tickles fans even if FAN is stopped
  pid           - configure the PID algorithm
  pid N p|i|d|sp|imin|imax|lo|hi  - configure PID paramaters
                                  - * Use correct FORMAT for numbers!
             p - set the PROPORTIONAL gain
             i - set the INTEGRAL gain
             d - set the DERIVATIVE gain
            sp - set SETPOINT
          imin - set I windup MIN value
          imax - set I windup MAX value
            lo - set output LOW limit
            hi - set output HIGH lmit
 MISC
  rate X        - Change rate to X ms polling (default 3000)
  ramp          - Force a RAMP condition
  dump          - Dump all the fan registers in raw HEX format
  hyst h v1..vN - Perform a test hysteresis with supplied numbers
  desc <0>..<15> - try to decode then execute raw descriptor bytes (5 or 16)
  actn <0>..<15> - try to decode then execute raw action bytes (5 or 16)
  debug trace|t X|h X|a X|g X|p X|off|on
                - Set the fine control values for the fan FYI level
  DIMM          - DIMM-specific subcommand handler
  DRIVE         - Drive temperature subcommand handler
  MB            - Memory buffer subcommand handler
  PECI          - PECI subcommand handler
 AWAITING DOCUMENTAION
  ms  - multi-segment info
  a N  - algorithms - set parameters for multi-segment.
  w   - weighting

