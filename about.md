layout: page
title: "About "
permalink: /about/
## About

    import platform
    print(f"\n{platform.platform()}  python version: {platform.version()}\n")

    def get_data(ritemnumber):
        ret_vals=[]
        with pyodbc.connect(cnstring) as cn:
            with cn.cursor() as cur:
                selectstring = f"select crm_job_no,cr_date,service_type,message,ritm_number from crm_job_external WITH (NOLOCK) where ritm_number=( ?) " 

                cur.execute(selectstring, ritemnumber)

                col = [column[0] for column in cur.description]

                rec =  cur.fetchall()

                for i in rec:
                    r = dict(zip(col,i))
                    ret_vals.append(r)
        return ret_vals
