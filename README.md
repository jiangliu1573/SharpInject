Android注入框架，使用注解实现，目前只支持View的注入，之后会加入事件注入

使用方法：
/**
 * Created by jiangliu on 2015/12/23.
 */
public class TestSharpInjectActivity extends Activity {

    // 注入View
    @Bind(R.id.btn_test)
    public Button mBtnTest;

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_test_sharp_inject);

        // 框架注入
        SharpInject.inject(this);

        initViews();
    }

    private void initViews() {
        mBtnTest.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(TestSharpInjectActivity.this, "Hello, test", Toast.LENGTH_SHORT).show();
            }
        });
    }
}
