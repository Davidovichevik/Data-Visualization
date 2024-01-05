# Data-Visualization
Data Visualization Dashboard with Dash (Plotly):
# app.py
import dash
import dash_core_components as dcc
import dash_html_components as html
import pandas as pd

app = dash.Dash(__name__)

# Load data
data = pd.read_csv('data.csv')

app.layout = html.Div(children=[
    html.H1(children='Data Visualization Dashboard'),

    dcc.Graph(
        id='example-graph',
        figure={
            'data': [
                {'x': data['x'], 'y': data['y'], 'type': 'scatter', 'mode': 'markers'},
            ],
            'layout': {
                'title': 'Scatter Plot',
            }
        }
    )
])

if __name__ == '__main__':
    app.run_server(debug=True)
