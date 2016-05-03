#PX4官方master对比更新（5.2）

##posctl

* <b>resetpos/alt的更改</b>
* 
 		pos_sp(0) = _pos(0);
 		pos_sp(1) = _pos(1);
 		pos_sp(2) = _pos(2);
		we have logic in the main function which chooses the velocity setpoint such that the 
		attitude setpoint is continuous when switching into velocity controlled mode, 
		therefore, we don't need to bother about resetting position in a special way. In 
		position control mode the position will be reset anyway until the vehicle has reduced speed.
***
* <b>添加了由非速度模式进入速度模式的判断并更改了vel_sp</b>（已应用于PV）
* 
		// check if we have switched from a non-velocity controlled mode into a velocity controlled mode
		// if yes, then correct xy velocity setpoint such that the attitude setpoint is continuous
		if (!control_vel_enabled_prev && _control_mode.flag_control_velocity_enabled) {

			/ choose velocity xyz setpoint such that the resulting thrust setpoint has the direction
			// given by the last attitude setpoint
			_vel_sp(0) = _vel(0) + (-PX4_R(_att_sp.R_body, 0, 2) * _att_sp.thrust - thrust_int(0) - _vel_err_d(0) * _params.vel_d(0)) / _params.vel_p(0);
			_vel_sp(1) = _vel(1) + (-PX4_R(_att_sp.R_body, 1, 2) * _att_sp.thrust - thrust_int(1) - _vel_err_d(1) * _params.vel_d(1)) / _params.vel_p(1);
			_vel_sp(2) = _vel(2) + (-PX4_R(_att_sp.R_body, 2, 2) * _att_sp.thrust - thrust_int(2) - _vel_err_d(2) * _params.vel_d(2)) / _params.vel_p(2);
			_vel_sp_prev(0) = _vel_sp(0);
			_vel_sp_prev(1) = _vel_sp(1);
			_vel_sp_prev(2) = _vel_sp(2);
			control_vel_enabled_prev = true;

			// compute updated velocity error
			vel_err = _vel_sp - _vel;
		}
***
* <b>添加了一个flag_control_acceleration_enabled控制标记</b>

	该控制标记在commander中添加，但是目前完全是false；

##attctl
<b>基本没有进行修改</b>

***
##inav
<b>基本没有进行修改</b>