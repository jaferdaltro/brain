---
apple-notes-id: C73A8212-6116-4C2B-AC8E-8CBF16887255
---
**station_column_enabled**


# New
(byebug) request.body.read
"station_column_id,override_enabled,override_lower_limit,override_upper_limit,override_default_l1_triage_id,override_default_fa_dri\n106,__NC__,__NC__,__NC__,__NC__,__NC__"

params
#<ActionController::Parameters {"station_id"=>"11", "build_id"=>"3", "controller"=>"api/v2/station_column_overrides", "action"=>"bulk_update"} permitted: false>

StationColumnOverrideBulkUpdateJob.new.perform(id, station.id, build.id, file_path) -> ok

![[Pasted Graphic 31.png]]


# OLd

(byebug) request.body.read
"station_column_id,override_enabled,override_lower_limit,override_upper_limit,override_default_l1_triage_id,override_default_fa_dri\n106,true,__NC__,__NC__,__NC__,__NC__"

(byebug) params
#<ActionController::Parameters {"station_id"=>"11", "build_id"=>"3", "controller"=>"api/v2/station_column_overrides", "action"=>"bulk_update"} permitted: false>

station_column_id,override_enabled,override_lower_limit,override_upper_limit
106                            ,false                         ,__NC__,__NC__


![[Pasted Graphic 1 15.png]]