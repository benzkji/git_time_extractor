[![Gem Version](https://badge.fury.io/rb/git_time_extractor.png)](http://badge.fury.io/rb/git_time_extractor)
[![Code Climate](https://codeclimate.com/github/rietta/git_time_extractor/badges/gpa.svg)](https://codeclimate.com/github/rietta/git_time_extractor)
# EXTRACT REASONABLE TIME RECORDS FROM A GIT REPOSITORY

This tool goes through a GIT repository's commit log and prints a CSV dump of per developer, per day working time based on a few assumptions:

 - A series of commits within a 3 hour window are part of the same development session
 - A single commit (or the first commit of the session) is considered to represent 30 minutes of work time
 - The more frequent a developer commits to the repository while working, the more accurate the time report will be

This script is based on previous code published publicly by *Sharad* at http://www.tatvartha.com/2010/01/generating-time-entry-from-git-log/. However, it has been adapted to run without Rails from the command line. The portions of the code written by Rietta are licensed under the terms of the BSD license (see section 3 below).


## 1. Prerequisites

This script is designed to work in Ruby 1.9 from the command line. It does not require Rails, but rather is design to work with pure Ruby and a couple of support gems, namely:

    - git
    - ostruct
    - logger
    - csv

Most of the requirements should be present on your base Ruby install.  However, you will need to first install a git gem.

For example, run the following:

    gem install git

## 2. Running

    cd /path/to/your/repository
    time_extract.rb > time_log.csv


## 3. LICENSE TERMS (BSD License)

Copyright (c) 2012, 2013, 2014 Rietta Inc. All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

