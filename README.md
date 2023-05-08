Here I show reproduction of my problem. Parcel is sitting in a child workspace with missing dependencies. If I run it with `npm -w apps/site run dev`, parcel will then install packages into the root instead of in the sub-module.

`git diff package.json`
```
diff --git a/package.json b/package.json
index 84ad63d..e87ec70 100644
--- a/package.json
+++ b/package.json
@@ -2,5 +2,8 @@
   "name": "parcel-workspaces-repro",
   "workspaces": [
     "apps/*"
-  ]
+  ],
+  "devDependencies": {
+    "@parcel/transformer-sass": "^2.8.3"
+  }
 }
```