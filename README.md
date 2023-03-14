# Fault-diagnosis-of-transformer-substations
Based on Comtrade format data of fault recorders

    <span style="color:#333333">``` class Log(object): 
    def __init__(self, txt_file): 
      self.orgstdout = sys.stdout   
      self.log = open(txt_file, "w") 
    def write(self, msg): 
      self.orgstdout.write(msg)   
      self.orgstdout.flush()   
      self.log.write(msg)   
      self.log.flush() 
    def flush(self): 
      pass 
    consoleLogDirectory = "xxx/consoleLog/"   
    try: 
      input_files_str = input() 
      auto_manu_state = eval(input()) 
      params_str = input() 
      if not os.path.exists(consoleLogDirectory):  # 判断文件夹是否已经存在 
        os.makedirs(consoleLogDirectory) 
      if auto_manu_state == 1: 
        sys.stdout = Log(consoleLogDirectory + "自动检测-..."+str(input_files_str[-10:]).replace("/","-").replace("\\","-")+"-+str(datetime.datetime.now()).replace(":","-")+ ".log") 
      else:
        sys.stdout = Log(consoleLogDirectory + "手动检测-..."+str(input_files_str[-10:]).replace("/","-").replace("\\","-")+"-+str(datetime.datetime.now()).replace(":","-")+ ".log") 
      input_files = input_files_str.split(",")     
      params_str_arr = params_str.split(",")     
      try: 
        params = list(map(int, params_str_arr))     
      except Exception as e: 
        print(e) 
        sys.exit() 
      if len(params)!=8: 
        print("输入参数数量异常，需要%d个，只得到%d个" % (8, len(params)))   
        sys.exit() 
      if auto_manu_state == 1: 
        AutoModule(input_files, params[:-2])    
      else: 
        ManuModule(input_files, params[-2:])
      except Exception as e: 
        print(e)```</span>
<div align=center><img src="https://github.com/chanchenwee/Fault-diagnosis-of-transformer-substations/blob/main/img/12-22%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C.jpg"  /></div>
<div align=center><img src="https://github.com/chanchenwee/Fault-diagnosis-of-transformer-substations/blob/main/img/12-312%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C.jpg" /></div>
<div align=center><img src="https://github.com/chanchenwee/Fault-diagnosis-of-transformer-substations/blob/main/img/12-32222%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C.jpg"  /></div>
<div align=center><img src="https://github.com/chanchenwee/Fault-diagnosis-of-transformer-substations/blob/main/img/12-3%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C.jpg"  /></div>
<div align=center><img src="https://github.com/chanchenwee/Fault-diagnosis-of-transformer-substations/blob/main/img/image-20230314154512674.png"  /></div>

