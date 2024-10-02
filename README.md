   await axios
        .post(`${BACKEND_API_URL}/signin`, formValues)
        .then((res) => {
          ajaxReqStatusSet(false);
          if (res.data.error == false) {
            console.log('----data-->>>>>', res.data);
            sessionStorage.setItem("auth_info", JSON.stringify(res.data));
            const path = res.data.tab[0].tab
            window.location.href = `${FRONTEND_APP_URL}${path}`;
            // history.push(`/${path}`)
          } else {
            swal({
              title: `${res.data.message}`,
              icon: "warning",
            });
          }
    <Route exact path="/" component={Dashboard} />
                  <Route exact path="/dashboard" component={Dashboard} />

                  <Route exact path="/crm" component={ModuleDetail} />

                  <Route exact path="/settings" component={ModuleDetail} />
                    <Route path="*">
                    <Redirect to="/" replace />
                  </Route>
