---
title: "Navigation and routing in React"
date: 2022-08-31T05:29:25+05:30
categories: ["Tutorial"]
---


## Adding navigation in UI

Creating a basic Category style navigation in react. We will try to create something like Azure devops.
This does not have a animations, we are only using the state to represent how sidenav should look.
Representing the navigation items as a list 

```
  const navigationItems = [
    {
      id: "board",
      title: "Boards",
      subNavigation: [
        { title: "Work items" },
        { title: "Sprint" },
        { title: "Queries" },
      ],
    },
    {
      id: "assistance",
      title: "Assistance",
      subNavigation: [{ title: "Help" }, { title: "About" }],
    },
  ];
```

Using state for selected navigation, since it changes on user interaction.
Here "board" is id of the navigation item
```
const [selectedNavigation, setSelectedNavigation] = useState("board");
```

Use the following template for creating a sidenav

```
<div>
      <div role="header">
        <h1 className="p-2">ADS clone</h1>
      </div>
      <div className="flex flex-row ">
        <div
          className="flex-col flex min-h-screen  w-60 border-r-2 border-black"
          role="navigation"
        >
          {navigationItems.map((nav) => (
            <div key={nav.id}>
              <button
                className="w-full text-left pl-1 border-y-2 border-slate-600"
                onClick={() => setSelectedNavigation(nav.id)}
              >
                {nav.title}
              </button>
              {selectedNavigation === nav.id && (
                <div className=" text-sm flex flex-col ">
                  {nav.subNavigation.map((subNav) => (
                    <a
                      className="px-3 py-1 border-b-2 border-slate-300"
                      href=""
                      key={subNav.title}
                    >
                      {subNav.title}
                    </a>
                  ))}
                </div>
              )}
            </div>
          ))}
        </div>
        <div className="flex-grow">Router outlet</div>
      </div>
    </div>
```

## Adding router

```
npm install react-router-dom@6
```

Create this in the parent component, in this example it is main.tsx
```
  <React.StrictMode>
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<App />}>
          <Route index element={<Home />} />
          <Route path="dashboard" element={<Dashboard />} />
          <Route path="grievances">
            <Route path="complaints" element={<Complaints />} />
            <Route path="query" element={<ComplaintsQuery />} />
          </Route>
          <Route path="grivances/query" element={<ComplaintsQuery />} />
        </Route>
      </Routes>
    </BrowserRouter>
  </React.StrictMode>
```

Add the component `Outlet` in the view port where the ouput of router should be displayed
```
  <div className="flex-grow">
    <Outlet />
  </div>
```
