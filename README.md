# corsTests

*igv.js-demos* has a makefile and a few simple html files which
demonstrate the mysterious failure to serve tbi of my flask/cors/byte-range
webserver on trena.systemsbiology.net

### depends on running a simple local webserver

file://xxx.html urls do not support CORS, so each of the demos is
loaded into a simple python webserver:  *make server*

## Files of interest

- **bed-tbi-broad.html**:  tbi works, loads quickly since byte ranges are employed
- **bed-tbi-trena.html**:  same files as at the broad, but tbi fails to load.  with tbi line
  commented out, igv.js tries to load the huge snp file, never
  completes, but does not fail
- **bed-tbi-trena-tiny.html**:  fails with tbi (indexURL) used, succeeds
  quickly with indexURL turned off
- **makefile**: a few targets to run the demos, including a python3 http server used by the
  other targets.
