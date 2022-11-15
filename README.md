# Stack Observability

### Dashboard Grafana

```` json
{
  "annotations": {
    "list": [
      {
        "builtIn": 1,
        "datasource": {
          "type": "grafana",
          "uid": "-- Grafana --"
        },
        "enable": true,
        "hide": true,
        "iconColor": "rgba(0, 211, 255, 1)",
        "name": "Annotations & Alerts",
        "target": {
          "limit": 100,
          "matchAny": false,
          "tags": [],
          "type": "dashboard"
        },
        "type": "dashboard"
      }
    ]
  },
  "editable": true,
  "fiscalYearStartMonth": 0,
  "graphTooltip": 0,
  "id": 2,
  "links": [],
  "liveNow": false,
  "panels": [
    {
      "collapsed": false,
      "gridPos": {
        "h": 1,
        "w": 24,
        "x": 0,
        "y": 0
      },
      "id": 2,
      "panels": [],
      "title": "API BASIC",
      "type": "row"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "description": "API uptime",
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "dark-blue",
                "value": 80
              }
            ]
          },
          "unit": "dthms"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 3,
        "w": 6,
        "x": 0,
        "y": 1
      },
      "id": 4,
      "options": {
        "colorMode": "value",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "textMode": "auto"
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "process_uptime_seconds{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\"}",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "UPTIME",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "description": "Hora da Inicialização da API",
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "dark-blue",
                "value": 80
              }
            ]
          },
          "unit": "dateTimeAsLocalNoDateIfToday"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 3,
        "w": 6,
        "x": 6,
        "y": 1
      },
      "id": 6,
      "options": {
        "colorMode": "value",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "textMode": "auto"
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "process_start_time_seconds{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\"} * 1000",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "START TIME",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 10,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 6,
        "w": 12,
        "x": 12,
        "y": 1
      },
      "id": 16,
      "options": {
        "legend": {
          "calcs": [
            "min",
            "max",
            "lastNotNull"
          ],
          "displayMode": "table",
          "placement": "right",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "hikaricp_connections_active{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\",pool=\"HikariPool-1\"}",
          "legendFormat": "active",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "hikaricp_connections_idle{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\",pool=\"HikariPool-1\"}",
          "hide": false,
          "legendFormat": "idle",
          "range": true,
          "refId": "B"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "hikaricp_connections_pending{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\",pool=\"HikariPool-1\"}",
          "hide": false,
          "legendFormat": "pending",
          "range": true,
          "refId": "C"
        }
      ],
      "title": "CONNECTION STATE",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "decimals": 0,
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 5
              }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 0,
        "y": 4
      },
      "id": 18,
      "options": {
        "colorMode": "value",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "textMode": "auto"
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "increase(hikaricp_connections_timeout_total{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\",pool=\"HikariPool-1\"}[1m])",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "DB CONNECTION TIMEOUT",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "decimals": 0,
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "orange",
                "value": 5
              },
              {
                "color": "red",
                "value": 10
              }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 3,
        "y": 4
      },
      "id": 14,
      "options": {
        "colorMode": "value",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "textMode": "auto"
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "increase(auth_user_error_total{application=\"app-forum-api\"}[1m])",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "AUTH ERRORS",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "decimals": 0,
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "green",
                "value": 80
              }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 6,
        "y": 4
      },
      "id": 12,
      "options": {
        "colorMode": "value",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "textMode": "auto"
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "increase(auth_user_success_total{application=\"app-forum-api\",}[1m])",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "USERS LOGGED",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "description": "Pool de conexões de JDBC",
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "dark-red",
                "value": null
              },
              {
                "color": "dark-green",
                "value": 10
              }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 3,
        "w": 3,
        "x": 9,
        "y": 4
      },
      "id": 10,
      "options": {
        "colorMode": "value",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "textMode": "auto"
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "hikaricp_connections{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\", pool=\"HikariPool-1\"}",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "JDBC POOL",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "description": "",
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 10,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          },
          "unit": "short"
        },
        "overrides": [
          {
            "matcher": {
              "id": "byName",
              "options": "warn"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "yellow",
                  "mode": "fixed"
                }
              }
            ]
          },
          {
            "matcher": {
              "id": "byName",
              "options": "{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\", level=\"error\"}"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "red",
                  "mode": "fixed"
                }
              }
            ]
          },
          {
            "matcher": {
              "id": "byName",
              "options": "error"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "red",
                  "mode": "fixed"
                }
              }
            ]
          },
          {
            "matcher": {
              "id": "byName",
              "options": "warm"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "yellow",
                  "mode": "fixed"
                }
              }
            ]
          }
        ]
      },
      "gridPos": {
        "h": 10,
        "w": 24,
        "x": 0,
        "y": 7
      },
      "id": 8,
      "options": {
        "legend": {
          "calcs": [
            "min",
            "max",
            "mean",
            "lastNotNull",
            "sum"
          ],
          "displayMode": "table",
          "placement": "right",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "increase(logback_events_total{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", level=\"warn\"}[5m])",
          "interval": "",
          "legendFormat": "warm",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "increase(logback_events_total{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", level=\"error\"}[5m])",
          "hide": false,
          "interval": "",
          "legendFormat": "error",
          "range": true,
          "refId": "B"
        }
      ],
      "title": "WARN & ERROR LOG",
      "type": "timeseries"
    },
    {
      "collapsed": false,
      "gridPos": {
        "h": 1,
        "w": 24,
        "x": 0,
        "y": 17
      },
      "id": 46,
      "panels": [],
      "title": "API USE",
      "type": "row"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "max": 100,
          "min": -3,
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "yellow",
                "value": 60
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          },
          "unit": "percent"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 4,
        "x": 0,
        "y": 18
      },
      "id": 38,
      "options": {
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showThresholdLabels": false,
        "showThresholdMarkers": true
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(jvm_memory_used_bytes{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\", area=\"heap\"}) * 100 / sum(jvm_memory_max_bytes{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\", area=\"heap\"})",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "HEAP USED",
      "type": "gauge"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 11,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "decimals": 0,
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          },
          "unit": "percent"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 20,
        "x": 4,
        "y": 18
      },
      "id": 42,
      "options": {
        "legend": {
          "calcs": [
            "min",
            "max",
            "lastNotNull"
          ],
          "displayMode": "table",
          "placement": "right",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "system_cpu_usage{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\"}",
          "legendFormat": "System CPU Usage",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "process_cpu_usage{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\"}",
          "hide": false,
          "legendFormat": "Proccess CPU Usage",
          "range": true,
          "refId": "B"
        }
      ],
      "title": "CPU UTILIZATION",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "max": 100,
          "min": 0,
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "yellow",
                "value": 60
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          },
          "unit": "percent"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 4,
        "x": 0,
        "y": 25
      },
      "id": 40,
      "options": {
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showThresholdLabels": false,
        "showThresholdMarkers": true
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(jvm_memory_used_bytes{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\", area=\"nonheap\"}) * 100 / sum(jvm_memory_max_bytes{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\", area=\"nonheap\"})",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "NON-HEAP USED",
      "type": "gauge"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 10,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "decimals": 0,
          "mappings": [],
          "min": 2,
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          },
          "unit": "percent"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 20,
        "x": 4,
        "y": 25
      },
      "id": 44,
      "options": {
        "legend": {
          "calcs": [
            "min",
            "max",
            "lastNotNull"
          ],
          "displayMode": "list",
          "placement": "right",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "system_load_average_1m{instance=\"app-forum-api:8080\", application=\"app-forum-api\", job=\"app-forum-api\"}",
          "legendFormat": "Load Avarage [1m]",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "system_cpu_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\"}",
          "hide": false,
          "legendFormat": "CPU Core Size",
          "range": true,
          "refId": "B"
        }
      ],
      "title": "LOAD AVERAGE",
      "type": "timeseries"
    },
    {
      "collapsed": false,
      "gridPos": {
        "h": 1,
        "w": 24,
        "x": 0,
        "y": 32
      },
      "id": 20,
      "panels": [],
      "title": "API RED",
      "type": "row"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "red",
                "value": null
              },
              {
                "color": "orange",
                "value": 30
              },
              {
                "color": "green",
                "value": 60
              }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 5,
        "w": 3,
        "x": 0,
        "y": 33
      },
      "id": 26,
      "options": {
        "colorMode": "value",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "textMode": "auto"
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(increase(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\"}[1m]))",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "TOTAL REQUEST",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "description": "",
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "decimals": 0,
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 3
              }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 5,
        "w": 3,
        "x": 3,
        "y": 33
      },
      "id": 22,
      "options": {
        "colorMode": "value",
        "graphMode": "none",
        "justifyMode": "auto",
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "textMode": "auto"
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(increase(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\",uri!=\"/actuator/prometheus\", status=\"200\"}[1m]))",
          "hide": false,
          "legendFormat": "error 200",
          "range": true,
          "refId": "B"
        }
      ],
      "title": "ERROR 500",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 10,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          },
          "unit": "s"
        },
        "overrides": [
          {
            "__systemRef": "hideSeriesFrom",
            "matcher": {
              "id": "byNames",
              "options": {
                "mode": "exclude",
                "names": [
                  "{application=\"app-forum-api\", exception=\"None\", instance=\"app-forum-api:8080\", job=\"app-forum-api\", le=\"+Inf\", method=\"POST\", outcome=\"CLIENT_ERROR\", status=\"400\", uri=\"/auth\"}"
                ],
                "prefix": "All except:",
                "readOnly": true
              }
            },
            "properties": [
              {
                "id": "custom.hideFrom",
                "value": {
                  "legend": false,
                  "tooltip": false,
                  "viz": true
                }
              }
            ]
          }
        ]
      },
      "gridPos": {
        "h": 5,
        "w": 18,
        "x": 6,
        "y": 33
      },
      "id": 30,
      "options": {
        "legend": {
          "calcs": [],
          "displayMode": "table",
          "placement": "right",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "histogram_quantile(0.99, sum(rate(http_server_requests_seconds_bucket{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[1m])) by (le))",
          "legendFormat": "99%",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "histogram_quantile(0.90, sum(rate(http_server_requests_seconds_bucket{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[1m])) by (le))",
          "hide": false,
          "legendFormat": "90%",
          "range": true,
          "refId": "B"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "histogram_quantile(0.75, sum(rate(http_server_requests_seconds_bucket{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[1m])) by (le))",
          "hide": false,
          "legendFormat": "75%",
          "range": true,
          "refId": "C"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "histogram_quantile(0.70, sum(rate(http_server_requests_seconds_bucket{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[1m])) by (le))",
          "hide": false,
          "legendFormat": "70%",
          "range": true,
          "refId": "D"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "histogram_quantile(0.25, sum(rate(http_server_requests_seconds_bucket{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[1m])) by (le))",
          "hide": false,
          "legendFormat": "25%",
          "range": true,
          "refId": "E"
        }
      ],
      "title": "LATENCY AVERAGE",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 11,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          },
          "unit": "s"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 24,
        "x": 0,
        "y": 38
      },
      "id": 28,
      "options": {
        "legend": {
          "calcs": [
            "min",
            "max",
            "mean",
            "firstNotNull"
          ],
          "displayMode": "table",
          "placement": "right",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "rate(http_server_requests_seconds_sum{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[1m]) / rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[1m])",
          "legendFormat": "{{uri}} {{method}} {{status}}",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "RESPONSE TIME",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 14,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          },
          "unit": "s"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 6,
        "w": 24,
        "x": 0,
        "y": 45
      },
      "id": 34,
      "options": {
        "legend": {
          "calcs": [
            "min",
            "max",
            "mean",
            "lastNotNull",
            "sum"
          ],
          "displayMode": "table",
          "placement": "right",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "rate(http_server_requests_seconds_sum{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", status=\"200\", uri=\"/topicos\"}[1m])  / rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", status=\"200\", uri=\"/topicos\"}[1m])",
          "legendFormat": "{{uri}} {{method}} {{status}}",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "rate(http_server_requests_seconds_sum{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", status=\"200\", uri=\"/topicos/{id}\"}[1m])  / rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", status=\"200\", uri=\"/topicos/{id}\"}[1m])",
          "hide": false,
          "legendFormat": "{{uri}} {{method}} {{status}}",
          "range": true,
          "refId": "B"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "rate(http_server_requests_seconds_sum{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", status=\"200\", uri=\"/auth\"}[1m])  / rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", status=\"200\", uri=\"/auth\"}[1m])",
          "hide": false,
          "legendFormat": "{{uri}} {{method}} {{status}}",
          "range": true,
          "refId": "C"
        }
      ],
      "title": "AVERAGE REQUEST DURATION",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 15,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 6,
        "w": 24,
        "x": 0,
        "y": 51
      },
      "id": 32,
      "options": {
        "legend": {
          "calcs": [
            "min",
            "max",
            "mean",
            "lastNotNull"
          ],
          "displayMode": "list",
          "placement": "right",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(increase(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri=\"/topicos\"}[1m]))",
          "legendFormat": "/topicos",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(increase(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri=\"/topicos/{id}\"}[1m]))",
          "hide": false,
          "legendFormat": "/topicos/{id}",
          "range": true,
          "refId": "B"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(increase(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri=\"/auth\"}[1m]))",
          "hide": false,
          "legendFormat": "/auth",
          "range": true,
          "refId": "C"
        }
      ],
      "title": "REQUEST COUNT",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 10,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "decimals": 0,
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          },
          "unit": "percentunit"
        },
        "overrides": [
          {
            "matcher": {
              "id": "byName",
              "options": "500"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "red",
                  "mode": "fixed"
                }
              }
            ]
          },
          {
            "matcher": {
              "id": "byName",
              "options": "400"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "orange",
                  "mode": "fixed"
                }
              }
            ]
          },
          {
            "matcher": {
              "id": "byName",
              "options": "404"
            },
            "properties": [
              {
                "id": "color",
                "value": {
                  "fixedColor": "yellow",
                  "mode": "fixed"
                }
              }
            ]
          }
        ]
      },
      "gridPos": {
        "h": 7,
        "w": 24,
        "x": 0,
        "y": 57
      },
      "id": 24,
      "options": {
        "legend": {
          "calcs": [
            "min",
            "max",
            "mean",
            "lastNotNull",
            "sum"
          ],
          "displayMode": "table",
          "placement": "right",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "pluginVersion": "9.2.4",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\", status=\"500\"}[5m])) / sum(rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[5m]))",
          "legendFormat": "500",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\", status=\"400\"}[5m])) / sum(rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[5m]))",
          "hide": false,
          "interval": "",
          "legendFormat": "400",
          "range": true,
          "refId": "B"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "sum(rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\", status=\"404\"}[5m])) / sum(rate(http_server_requests_seconds_count{application=\"app-forum-api\",instance=\"app-forum-api:8080\",job=\"app-forum-api\", uri!=\"/actuator/prometheus\"}[5m]))",
          "hide": false,
          "legendFormat": "404",
          "range": true,
          "refId": "C"
        }
      ],
      "title": "ERROR RATE",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "simRXgd4k"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 11,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              }
            ]
          },
          "unit": "s"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 5,
        "w": 24,
        "x": 0,
        "y": 64
      },
      "id": 36,
      "options": {
        "legend": {
          "calcs": [
            "min",
            "max",
            "lastNotNull",
            "mean",
            "sum"
          ],
          "displayMode": "list",
          "placement": "bottom",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "simRXgd4k"
          },
          "editorMode": "code",
          "expr": "http_server_requests_seconds_max{application=\"app-forum-api\", instance=\"app-forum-api:8080\", job=\"app-forum-api\", status=\"500\"}",
          "legendFormat": "{{uri}} {{method}} {{status}}",
          "range": true,
          "refId": "A"
        }
      ],
      "title": "MAX REQUEST DURATION",
      "type": "timeseries"
    }
  ],
  "refresh": "5s",
  "schemaVersion": 37,
  "style": "dark",
  "tags": [],
  "templating": {
    "list": [
      {
        "current": {
          "selected": false,
          "text": "app-forum-api",
          "value": "app-forum-api"
        },
        "definition": "label_values(application)",
        "hide": 0,
        "includeAll": false,
        "label": "application",
        "multi": false,
        "name": "application",
        "options": [],
        "query": {
          "query": "label_values(application)",
          "refId": "StandardVariableQuery"
        },
        "refresh": 1,
        "regex": "",
        "skipUrlSync": false,
        "sort": 0,
        "type": "query"
      },
      {
        "current": {
          "selected": false,
          "text": "app-forum-api:8080",
          "value": "app-forum-api:8080"
        },
        "definition": "label_values(jvm_classes_loaded_classes{application=\"$application\"}, instance)",
        "hide": 0,
        "includeAll": false,
        "label": "instance",
        "multi": false,
        "name": "instance",
        "options": [],
        "query": {
          "query": "label_values(jvm_classes_loaded_classes{application=\"$application\"}, instance)",
          "refId": "StandardVariableQuery"
        },
        "refresh": 1,
        "regex": "",
        "skipUrlSync": false,
        "sort": 0,
        "type": "query"
      },
      {
        "current": {
          "selected": false,
          "text": "HikariPool-1",
          "value": "HikariPool-1"
        },
        "definition": "label_values(hikaricp_connections{instance=\"$instance\", application=\"$application\"}, pool)",
        "hide": 0,
        "includeAll": false,
        "label": "pool",
        "multi": false,
        "name": "pool",
        "options": [],
        "query": {
          "query": "label_values(hikaricp_connections{instance=\"$instance\", application=\"$application\"}, pool)",
          "refId": "StandardVariableQuery"
        },
        "refresh": 1,
        "regex": "",
        "skipUrlSync": false,
        "sort": 0,
        "type": "query"
      }
    ]
  },
  "time": {
    "from": "now-5m",
    "to": "now"
  },
  "timepicker": {},
  "timezone": "",
  "title": "dashboard-forum-api",
  "uid": "JUgGugd4k",
  "version": 33,
  "weekStart": ""
}
````