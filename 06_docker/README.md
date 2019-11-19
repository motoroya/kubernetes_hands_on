# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


```
app_1  | => Booting Puma
app_1  | => Rails 6.0.1 application starting in development 
app_1  | => Run `rails server --help` for more startup options
app_1  | Exiting
app_1  | Traceback (most recent call last):
app_1  | 	68: from bin/rails:4:in `<main>'
app_1  | 	67: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:325:in `require'
app_1  | 	66: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:291:in `load_dependency'
app_1  | 	65: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:325:in `block in require'
app_1  | 	64: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
app_1  | 	63: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
app_1  | 	62: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
app_1  | 	61: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
app_1  | 	60: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
app_1  | 	59: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands.rb:18:in `<main>'
app_1  | 	58: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/command.rb:46:in `invoke'
app_1  | 	57: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/command/base.rb:65:in `perform'
app_1  | 	56: from /usr/local/bundle/gems/thor-0.20.3/lib/thor.rb:387:in `dispatch'
app_1  | 	55: from /usr/local/bundle/gems/thor-0.20.3/lib/thor/invocation.rb:126:in `invoke_command'
app_1  | 	54: from /usr/local/bundle/gems/thor-0.20.3/lib/thor/command.rb:27:in `run'
app_1  | 	53: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:138:in `perform'
app_1  | 	52: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:138:in `tap'
app_1  | 	51: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:147:in `block in perform'
app_1  | 	50: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:37:in `start'
app_1  | 	49: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:77:in `log_to_stdout'
app_1  | 	48: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/server.rb:354:in `wrapped_app'
app_1  | 	47: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/server.rb:219:in `app'
app_1  | 	46: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/server.rb:319:in `build_app_and_options_from_config'
app_1  | 	45: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:40:in `parse_file'
app_1  | 	44: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in `new_from_string'
app_1  | 	43: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in `eval'
app_1  | 	42: from config.ru:in `<main>'
app_1  | 	41: from config.ru:in `new'
app_1  | 	40: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in `initialize'
app_1  | 	39: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in `instance_eval'
app_1  | 	38: from config.ru:3:in `block in <main>'
app_1  | 	37: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:48:in `require_relative'
app_1  | 	36: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:325:in `require'
app_1  | 	35: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:291:in `load_dependency'
app_1  | 	34: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:325:in `block in require'
app_1  | 	33: from /usr/local/bundle/gems/zeitwerk-2.2.1/lib/zeitwerk/kernel.rb:23:in `require'
app_1  | 	32: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
app_1  | 	31: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
app_1  | 	30: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
app_1  | 	29: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
app_1  | 	28: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
app_1  | 	27: from /app/config/environment.rb:5:in `<main>'
app_1  | 	26: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/application.rb:363:in `initialize!'
app_1  | 	25: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/initializable.rb:60:in `run_initializers'
app_1  | 	24: from /usr/local/lib/ruby/2.6.0/tsort.rb:205:in `tsort_each'
app_1  | 	23: from /usr/local/lib/ruby/2.6.0/tsort.rb:226:in `tsort_each'
app_1  | 	22: from /usr/local/lib/ruby/2.6.0/tsort.rb:347:in `each_strongly_connected_component'
app_1  | 	21: from /usr/local/lib/ruby/2.6.0/tsort.rb:347:in `call'
app_1  | 	20: from /usr/local/lib/ruby/2.6.0/tsort.rb:347:in `each'
app_1  | 	19: from /usr/local/lib/ruby/2.6.0/tsort.rb:349:in `block in each_strongly_connected_component'
app_1  | 	18: from /usr/local/lib/ruby/2.6.0/tsort.rb:431:in `each_strongly_connected_component_from'
app_1  | 	17: from /usr/local/lib/ruby/2.6.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component'
app_1  | 	16: from /usr/local/lib/ruby/2.6.0/tsort.rb:228:in `block in tsort_each'
app_1  | 	15: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/initializable.rb:61:in `block in run_initializers'
app_1  | 	14: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/initializable.rb:32:in `run'
app_1  | 	13: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/initializable.rb:32:in `instance_exec'
app_1  | 	12: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/railtie.rb:84:in `block in <class:Engine>'
app_1  | 	11: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker.rb:27:in `bootstrap'
app_1  | 	10: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/commands.rb:31:in `bootstrap'
app_1  | 	 9: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/manifest.rb:18:in `refresh'
app_1  | 	 8: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/manifest.rb:83:in `load'
app_1  | 	 7: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:51:in `public_manifest_path'
app_1  | 	 6: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:47:in `public_output_path'
app_1  | 	 5: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:43:in `public_path'
app_1  | 	 4: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:84:in `fetch'
app_1  | 	 3: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:88:in `data'
app_1  | 	 2: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:92:in `load'
app_1  | 	 1: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:92:in `read'
app_1  | /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:92:in `read': No such file or directory @ rb_sysopen - /app/config/webpacker.yml (Errno::ENOENT)
app_1  | 	67: from bin/rails:4:in `<main>'
app_1  | 	66: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:325:in `require'
app_1  | 	65: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:291:in `load_dependency'
app_1  | 	64: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:325:in `block in require'
app_1  | 	63: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
app_1  | 	62: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
app_1  | 	61: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
app_1  | 	60: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
app_1  | 	59: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
app_1  | 	58: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands.rb:18:in `<main>'
app_1  | 	57: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/command.rb:46:in `invoke'
app_1  | 	56: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/command/base.rb:65:in `perform'
app_1  | 	55: from /usr/local/bundle/gems/thor-0.20.3/lib/thor.rb:387:in `dispatch'
app_1  | 	54: from /usr/local/bundle/gems/thor-0.20.3/lib/thor/invocation.rb:126:in `invoke_command'
app_1  | 	53: from /usr/local/bundle/gems/thor-0.20.3/lib/thor/command.rb:27:in `run'
app_1  | 	52: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:138:in `perform'
app_1  | 	51: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:138:in `tap'
app_1  | 	50: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:147:in `block in perform'
app_1  | 	49: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:37:in `start'
app_1  | 	48: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/commands/server/server_command.rb:77:in `log_to_stdout'
app_1  | 	47: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/server.rb:354:in `wrapped_app'
app_1  | 	46: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/server.rb:219:in `app'
app_1  | 	45: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/server.rb:319:in `build_app_and_options_from_config'
app_1  | 	44: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:40:in `parse_file'
app_1  | 	43: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in `new_from_string'
app_1  | 	42: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:49:in `eval'
app_1  | 	41: from config.ru:in `<main>'
app_1  | 	40: from config.ru:in `new'
app_1  | 	39: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in `initialize'
app_1  | 	38: from /usr/local/bundle/gems/rack-2.0.7/lib/rack/builder.rb:55:in `instance_eval'
app_1  | 	37: from config.ru:3:in `block in <main>'
app_1  | 	36: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:48:in `require_relative'
app_1  | 	35: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:325:in `require'
app_1  | 	34: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:291:in `load_dependency'
app_1  | 	33: from /usr/local/bundle/gems/activesupport-6.0.1/lib/active_support/dependencies.rb:325:in `block in require'
app_1  | 	32: from /usr/local/bundle/gems/zeitwerk-2.2.1/lib/zeitwerk/kernel.rb:23:in `require'
app_1  | 	31: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
app_1  | 	30: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
app_1  | 	29: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
app_1  | 	28: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
app_1  | 	27: from /usr/local/bundle/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
app_1  | 	26: from /app/config/environment.rb:5:in `<main>'
app_1  | 	25: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/application.rb:363:in `initialize!'
app_1  | 	24: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/initializable.rb:60:in `run_initializers'
app_1  | 	23: from /usr/local/lib/ruby/2.6.0/tsort.rb:205:in `tsort_each'
app_1  | 	22: from /usr/local/lib/ruby/2.6.0/tsort.rb:226:in `tsort_each'
app_1  | 	21: from /usr/local/lib/ruby/2.6.0/tsort.rb:347:in `each_strongly_connected_component'
app_1  | 	20: from /usr/local/lib/ruby/2.6.0/tsort.rb:347:in `call'
app_1  | 	19: from /usr/local/lib/ruby/2.6.0/tsort.rb:347:in `each'
app_1  | 	18: from /usr/local/lib/ruby/2.6.0/tsort.rb:349:in `block in each_strongly_connected_component'
app_1  | 	17: from /usr/local/lib/ruby/2.6.0/tsort.rb:431:in `each_strongly_connected_component_from'
app_1  | 	16: from /usr/local/lib/ruby/2.6.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component'
app_1  | 	15: from /usr/local/lib/ruby/2.6.0/tsort.rb:228:in `block in tsort_each'
app_1  | 	14: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/initializable.rb:61:in `block in run_initializers'
app_1  | 	13: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/initializable.rb:32:in `run'
app_1  | 	12: from /usr/local/bundle/gems/railties-6.0.1/lib/rails/initializable.rb:32:in `instance_exec'
app_1  | 	11: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/railtie.rb:84:in `block in <class:Engine>'
app_1  | 	10: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker.rb:27:in `bootstrap'
app_1  | 	 9: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/commands.rb:31:in `bootstrap'
app_1  | 	 8: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/manifest.rb:18:in `refresh'
app_1  | 	 7: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/manifest.rb:83:in `load'
app_1  | 	 6: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:51:in `public_manifest_path'
app_1  | 	 5: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:47:in `public_output_path'
app_1  | 	 4: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:43:in `public_path'
app_1  | 	 3: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:84:in `fetch'
app_1  | 	 2: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:88:in `data'
app_1  | 	 1: from /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:91:in `load'
app_1  | /usr/local/bundle/gems/webpacker-4.2.0/lib/webpacker/configuration.rb:95:in `rescue in load': Webpacker configuration file not found /app/config/webpacker.yml. Please run rails webpacker:install Error: No such file or directory @ rb_sysopen - /app/config/webpacker.yml (RuntimeError)
06_docker_app_1 exited with code 1


####

#### エラーメッセージに従いインストール実行

~$ docker-compose run app bundle exec rails webpacker:install
Starting 06_docker_db_1 ... done
sh: 1: node: not found
sh: 1: nodejs: not found
Node.js not installed. Please download and install Node.js https://nodejs.org/en/download/
```

```
#### Dockerfile側にnodejsのインストールがないため修正

E: Unable to locate package nodejs

# https://github.com/nodesource/distributions/blob/master/README.md
# を参照し、apt-get install -y nodejs実行前に
# RUN curl -sL https://deb.nodesource.com/setup_13.x | bash -
# を追記

```


```
$ docker image rm -f 573128995f98
Untagged: 06_app:latest
Deleted: sha256:573128995f98f0a3517aaf2984390eda06c841e97d07f4b86dd35ad8818d36f7
Deleted: sha256:b2d89eaf37d2e904e59d5618a5b0bef53c5ab3ec55af45dfd1ffdd8eb563d4f2
Deleted: sha256:8ac7ae32f35ea122a451a64195b7ccc93568f408e0b5e48047c361e133b772bc
Deleted: sha256:e29ecfc0bca5428ff4cf8b0730c1f7ea3a15f363c7d07f33c9297d2cecbb654a
Deleted: sha256:ffbcba1fa43f140d87950a6861ad89a5c8d58e99e90ee1ab02594ab3469f46cf
jiraffe40095noMacBook-puro:06_docker jiraffe40095$ docker-compose build --no-cache
db uses an image, skipping
Building app
Step 1/9 : FROM ruby:latest
 ---> d98e4013532b
Step 2/9 : RUN apt-get update &&     apt-get install -y build-essential
 ---> Running in 7bd6c0471b97
Get:1 http://security.debian.org/debian-security buster/updates InRelease [65.4 kB]
Err:1 http://security.debian.org/debian-security buster/updates InRelease
  Error writing to output file - write (28: No space left on device) [IP: 151.101.88.204 80]
Get:2 http://deb.debian.org/debian buster InRelease [122 kB]
Err:2 http://deb.debian.org/debian buster InRelease
  Error writing to output file - write (28: No space left on device) [IP: 151.101.88.204 80]
Get:3 http://deb.debian.org/debian buster-updates InRelease [49.3 kB]
Err:3 http://deb.debian.org/debian buster-updates InRelease
  Error writing to output file - write (28: No space left on device) [IP: 151.101.88.204 80]
Reading package lists...
W: Failed to fetch http://deb.debian.org/debian/dists/buster/InRelease  Error writing to output file - write (28: No space left on device) [IP: 151.101.88.204 80]
W: Failed to fetch http://security.debian.org/debian-security/dists/buster/updates/InRelease  Error writing to output file - write (28: No space left on device) [IP: 151.101.88.204 80]
W: Failed to fetch http://deb.debian.org/debian/dists/buster-updates/InRelease  Error writing to output file - write (28: No space left on device) [IP: 151.101.88.204 80]
W: Some index files failed to download. They have been ignored, or old ones used instead.
Reading package lists...
Building dependency tree...
Reading state information...
Package build-essential is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'build-essential' has no installation candidate


####  docker system prune を行い解消
https://github.com/tianon/docker-brew-ubuntu-core/issues/132
```

```
# 改めて webpacker:install実行

~$ docker-compose run app bundle exec rails webpacker:install
Starting 06_docker_db_1 ... done
Yarn not installed. Please download and install Yarn from https://yarnpkg.com/lang/en/docs/install/

# Dockerfile 側に apt-get install -y yarn を追記

# build 中に yanr のインストールコマンドのセットが表示されたためsodoを除去し以下を追記

RUN curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
    apt-get update && apt-get install -y yarn
```

```
# 改めて webpacker:install実行
~$ docker-compose run app bundle exec rails webpacker:install


# 完了
```

```
~$ docker-compose up
app_1  | => Booting Puma
app_1  | => Rails 6.0.1 application starting in development 
app_1  | => Run `rails server --help` for more startup options
app_1  | Puma starting in single mode...
app_1  | * Version 4.3.0 (ruby 2.6.5-p114), codename: Mysterious Traveller
app_1  | * Min threads: 5, max threads: 5
app_1  | * Environment: development
app_1  | * Listening on tcp://127.0.0.1:3000
app_1  | Use Ctrl-C to stop

# 127.0.0.1 で起動しているため docker-compose.yml 側の command を `rails s -b 0` に修正

```