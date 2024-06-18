The project is a Django-based REST API designed to handle user registration, authentication, marking phone numbers as spam. It utilizes Django's ORM for relational database management and Django REST Framework for building API endpoints.


### HOW TO RUN THIS API ?
 1) Create a virtual environment (optionl)
 2) Install the dependencies mentioned in requirements.txt
 3) Run using "Python manage.py runserver"
    #Follow spam_detection\urls.py file for endpoints
    #Follow tests\test_spam_detection.py for sample input
 4) Send Post request to user-registration endpoint to register user.
 5) Go to api\Auth_token.py and create your own auth token and add it to header of the request.
 6) Now feel free to use all other services.


### ENDPOINT DETAILS

path('admin/', admin.site.urls),

## USE THIS ENDPOINT TO REGISTER ANY USER (POST) 
path('api/register/', views.user_registration, name='user-registration'),

## USE THIS ENDPOINT TO SEE ALL REGISTERED USERS (GET)
path('api/users/', views.user_list, name='user-list'),

## USE THIS ENDPOINT TO VIEW AND DELETE A PARTICULAR USER BY PROVIDING ID (GET)
path('api/users/<int:id>/', views.user_detail, name='user-detail'),

## USE THIS ENDPOINT TO ADD PERSONAL CONTACT FROM A USERS ACCOUNT(POST)
path('api/addcontact/', views.add_contact, name='add_contact'),
    
## USE THIS ENDPOINT TO SEARCH BY GIVING QUERY AND PHONE_NUMBER (GET)
path('api/search/', views.search_by_input, name='search_by_input'),

## USE THIS ENDPOINT TO VIEW CONTACT INFO OF PERSON WHO IS SPAM AND IS PRESENT IN  CONTACT(GET)   
path('api/contactinfo/', views.get_contact_details, name='details'),

## USE THIS ENDPOINT TO REPORT A SPAM(GET)
path('api/spam/register/', views.register_spam, name='register-spam'),

## USE THIS ENDPOINT TO SEE ALL SPAM NUMBERS (GET)
path('api/spams/', views.spam_list, name='spam-list'),

## USE THIS ENDPOINT TO CHECK IF NUMBER IS SPAM OR NOT (GET)
path('api/spam/check/<str:phone_number>/', views.check_spam, name='check-spam'),

## USE THESE ENDPOINTS TO GET AUTH TOKEN(POST)
path('api/token/', TokenObtainPairView.as_view(), name='token_obtain_pair'),
path('api/token/refresh/', TokenRefreshView.as_view(), name='token_refresh'),

