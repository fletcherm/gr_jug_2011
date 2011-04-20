!SLIDE 
# Ruby for Desktop Applications? Yes we can. #

!SLIDE
## (from Mike Karlesky) ##

!SLIDE center
# Matt Fletcher #
# Atomic Object #
![AO](AO-symbol-color.png)

!SLIDE center
![AGI](agi_logo.png)

!SLIDE
## DOS simulators => Java + JRuby simulators ##

!SLIDE
# Demos! #

!SLIDE
# Techs #

!SLIDE
# Java #

!SLIDE
## (we all know what that is) ##

!SLIDE
# [JRuby](www.jruby.org) #

!SLIDE
## Ruby interpreter on the JVM ##

!SLIDE
## Production Simulator - JRuby 1.0 (2007) ##

!SLIDE
## Write Ruby ##
    @@@ Ruby
    class ConfigurationFacade
      constructor :config

      def method_missing(key, *args, &block)
        @config[key.to_s]
      end

      def capital_investment
        @config["capital_investment"].present?
          ? @configuration["capital_investment"]
          : 0
      end
    end

!SLIDE
## Interface with Java ##
    @@@ Ruby
    class AgingReportView
      def view(parent)
        @table_model = ReadOnlyTableModel.new
        @aging = JTable.new(@table_model)
        @aging.row_selection_allowed = false
        @aging.cell_selection_enabled = true
      end
    end

!SLIDE
## Cross-pollinate for maximum goodness ##
    @@@ Ruby
    def invoke_later(&block)
      if javax.swing.SwingUtilities.
                     is_event_dispatch_thread
        block.call
      else
        ...
      end
    end

!SLIDE
    @@@ Ruby
    SwingUtilities.invoke_later(Runnable.impl do
      begin
        block.call
      rescue Exception => ex
        puts ex.message
        puts ex.backtrace.join("\n")
      end
    end)

!SLIDE
    @@@ Ruby
    def add_row(row)
      invoke_later do
        @table_model.add_row row.to_java
      end
    end

    def clear_rows
      invoke_later do
        @table_model.clear
      end
    end

!SLIDE
# RSpec for testing #
## 2120 unit tests ##
## 286 system tests ##

!SLIDE bullets incremental
# Core libs #
* Hardmock - mocking library (retired)
* Constructor - object construction
* DIY - dependency injection

!SLIDE
# Substance - look and feel #

!SLIDE
# Apache Batik - SVG #

!SLIDE
# Java scenegraph #

!SLIDE
# JFreeChart #

!SLIDE
# Beta distribution #

!SLIDE
# Bouncy Castle - encryption #

!SLIDE
# YAML - configuration #

!SLIDE
# NSIS - Windows installer #

!SLIDE
# Launch4J - Windows Java app launcher #

!SLIDE
# .app bundle on Mac #

!SLIDE
# shell script on Linux #

!SLIDE
# Development #

!SLIDE
# Presenter First #
