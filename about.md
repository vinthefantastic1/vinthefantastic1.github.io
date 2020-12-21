layout: page
title: "About "
permalink: /about/
## About

`import platform`

`print(f"\n{platform.platform()}  python version: {platform.version()}\n")`

    
    cur.execute(selectstring, payment_request_id)
    
    rec = cur.fetchall()
    
    col = [column[0] for column in cur.description]
    
    for item in rec:
      r = dict(zip(col,item))
      pp.pprint(r)
