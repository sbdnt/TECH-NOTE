# POST DATA WORKFLOW

## 001.Request send from client


## 002.Middleware class
    "corsheaders.middleware.CorsMiddleware",
    "django.middleware.security.SecurityMiddleware",
    "django.contrib.sessions.middleware.SessionMiddleware",
    "django.middleware.common.CommonMiddleware",
    "django.middleware.csrf.CsrfViewMiddleware",
    "django.contrib.auth.middleware.AuthenticationMiddleware",
    "django.contrib.messages.middleware.MessageMiddleware",
    "django.middleware.clickjacking.XFrameOptionsMiddleware",
    "oauth2_provider.middleware.OAuth2TokenMiddleware",
    "django_user_agents.middleware.UserAgentMiddleware",
    "app.core.context.AppContextMiddleware",
    "app.devices.middleware.DeviceIDLoggerMiddleware",
    ....

## 003.URL dispatcher
Dưới đây là giải thích về ý nghĩa của mỗi thuộc tính và giá trị trong danh sách bạn đã cung cấp:

1. **`allowed_methods = <property object at 0x7f0c527b2130>` (APIView)**: Thuộc tính này xác định các phương thức HTTP được phép sử dụng trên view.

2. **`authentication_classes = [<class 'rest_framework.authentication.SessionAuthentication'>, <class 'rest_framework.authentication.BasicAuthentication'>]` (APIView)**: Xác định lớp xác thực người dùng nào được sử dụng để xác thực request.

3. **`content_negotiation_class = <class 'rest_framework.negotiation.DefaultContentNegotiation'>` (APIView)**: Xác định lớp xử lý đàm phán về nội dung để xác định định dạng dữ liệu phù hợp.

4. **`default_response_headers = <property object at 0x7f0c527b2b30>` (APIView)**: Thuộc tính này định nghĩa các header mặc định cho response trả về cho client.

5. **`filter_backends = []` (GenericAPIView)**: Xác định các lớp xử lý filter mà view sử dụng để lọc dữ liệu queryset.

6. **`http_method_names = ['get', 'post', 'put', 'patch', 'delete', 'head', 'options', 'trace']` (View)**: Liệt kê các phương thức HTTP mà view hỗ trợ.

7. **`lookup_field = 'pk'` (GenericAPIView)**: Xác định trường sẽ được sử dụng để tìm kiếm một đối tượng cụ thể trong queryset.

8. **`lookup_url_kwarg = None` (GenericAPIView)**: Xác định tham số URL mà sẽ chứa giá trị trường tìm kiếm (lookup field).

9. **`metadata_class = <class 'rest_framework.metadata.SimpleMetadata'>` (APIView)**: Xác định lớp xử lý metadata cho API view.

10. **`pagination_class = None` (GenericAPIView)**: Xác định lớp xử lý phân trang dữ liệu.

11. **`paginator = <property object at 0x7f0c52d0a1d0>` (GenericAPIView)**: Thuộc tính này định nghĩa cách phân trang dữ liệu trong API view.

12. **`parser_classes = [<class 'rest_framework.parsers.JSONParser'>, <class 'rest_framework.parsers.FormParser'>, <class 'rest_framework.parsers.MultiPartParser'>]` (APIView)**: Xác định các lớp xử lý phân tích dữ liệu request từ client.

13. **`permission_classes = [<class 'rest_framework.permissions.AllowAny'>]` (APIView)**: Xác định các lớp kiểm tra quyền truy cập cho view.

14. **`queryset = None` (GenericAPIView)**: Xác định queryset mà view sử dụng để truy xuất dữ liệu.

15. **`renderer_classes = [<class 'rest_framework.renderers.JSONRenderer'>, <class 'rest_framework.renderers.BrowsableAPIRenderer'>]` (APIView)**: Xác định các lớp xử lý render dữ liệu response.

16. **`schema = <rest_framework.schemas.openapi.AutoSchema object at 0x7f0c52776b20>` (APIView)**: Xác định schema cho API view.

17. **`serializer_class = None` (GenericAPIView)**: Xác định lớp serializer mà view sử dụng để xử lý dữ liệu.

18. **`settings = <rest_framework.settings.APISettings object at 0x7f0c52ad0a90>` (APIView)**: Xác định cấu hình API cho view.

19. **`throttle_classes = []` (APIView)**: Xác định các lớp throttle mà view sử dụng để kiểm soát tần suất truy cập.

20. **`versioning_class = None` (APIView)**: Xác đđịnh lớp xử lý versioning cho view.

21. **`view_is_async = False`**: Xác định xem view có được thực thi bất đồng bộ hay không.

Các thông tin trên giúp xác định các cấu hình và chức năng của một API view trong Django REST framework.

     



