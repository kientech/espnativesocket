# 4. Flex Wrap

`Flex Wrap` là một thuộc tính trong CSS Flexbox được sử dụng để kiểm soát cách các mục linh hoạt sẽ tự động xuống dòng khi không gian trong container flex không đủ để chứa tất cả các mục. Thuộc tính này quyết định xem liệu các mục con sẽ được đặt trên cùng một dòng hoặc được phân bổ vào các dòng mới khi không gian bị hạn chế.

| Class            | Properties                     |
|------------------|--------------------------------|
| flex-wrap        | `flex-wrap: wrap;`             |
| flex-wrap-reverse| `flex-wrap: wrap-reverse;`     |
| flex-nowrap      | `flex-wrap: nowrap;`           |


-   **flex-wrap**:

    -   Class này áp dụng thuộc tính flex-wrap: wrap

    -   Thuộc tính flex-wrap: wrap; cho biết rằng các mục trong container flex sẽ tự động xuống dòng nếu không gian không đủ để chứa tất cả các mục trên cùng một dòng.

-   **flex-wrap-reverse**

    -   Class này áp dụng thuộc tính flex-wrap: wrap-reverse;

    -   Thuộc tính flex-wrap: wrap-reverse; sẽ đảo ngược hướng xuống dòng, điều này có nghĩa là các mục sẽ tự động xuống dòng từ dưới lên trên nếu không gian không đủ.

-   **flex-nowrap:**

    -   Class này áp dụng thuộc tính flex-wrap: nowrap

    -   Thuộc tính flex-wrap: nowrap; ngăn các mục tự động xuống dòng, và thay vào đó, chúng sẽ bị co lại hoặc tràn ra ngoài container flex nếu không đủ không gian.