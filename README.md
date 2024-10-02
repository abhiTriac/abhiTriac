 <Route exact path="/" render={() => <Redirect to="/dashboard" />} />
                    
    <Route path="*">
                        <Redirect to="/dashboard" replace />
                    </Route>
