#linux指令
> ls -alt # 按修改时间排序
> ls --sort=time -la # 等价于> ls -alt
> ls -alc # 按创建时间排序
> ls -alu # 按访问时间排序
 
# 以上均可使用-r实现逆序排序
> ls -alrt # 按修改时间排序
> ls --sort=time -lra # 等价于> ls -alrt
> ls -alrc # 按创建时间排序
> ls -alru # 按访问时间排序
 
# 也可以查找指定类型的文件，然后指定按时间排序
> find . -name *.php|xargs ls -alt

如： find 路径 -name "*.c" -exec cp {} 目标目录 \;