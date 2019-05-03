#ConstraintLayout QuickStart
> 필수기능만 빠르게 경험하기. Constraint는 압박이란 뜻으로 View의 위치를 압박으로 지정한다. 마치 줄로 사방을 연결한다고 생각하면 된다. 

1. 위치를 지정하는 Constraint 지정 프로퍼티 

영어문장처럼 이해하면 쉽다. 
~~~xml
app:layout_constraint[시작]_to[종착]of="View"
~~~

example
~~~xml
    app:layout_constraintLeft_toLeftOf="parent"
    app:layout_constraintTop_toTopOf="parent"
    app:layout_constraintRight_toLeftOf="parent"
    app:layout_constraintBottom_toBottomOf="parent"
~~~

- 사방에 압박을 하지않을 경우, 때에따라 붉은색으로 경고메시지를 보여준다. 

2. bias는 위치관련 비율이다. 

~~~xml
0.5 중간 
0.0 왼쪽 
1.0 오른쪽 
~~~
을 기준으로 값을 변경하여 비율로 이동한다. 

example

~~~xml
app:layout_constraintHorizontal_bias="0.0"
app:layout_constraintVertical_bias="0.224"
~~~

3. 전체크기는 match_parents가 아니라 match_constraint이며 0dp로 표시한다. 

디자인모드에서 constraint를 클릭하며 wrap, fixed, match 형식으로 설정할 수도 있다. 

~~~xml
android:layout_width="0dp"
~~~

4. 크기 및 절대값 이동은 margin으로 처리

~~~xml
<Button
            android:text="4. bias 1.0 margin 20"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:id="@+id/button2"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            android:layout_marginBottom="32dp"
            app:layout_constraintStart_toEndOf="@+id/button3"
            android:layout_marginRight="20dp"
            app:layout_constraintHorizontal_bias="1.0"/>
~~~

5. 가로세로 비율 

가로 또는 세로 중 하나는 0dp이어야 한다.  
~~~xml
app:layout_constraintDimensionRatio = 가로:세로
~~~

~~~xml
<!--app:layout_constraintDimensionRatio = 가로:세로-->
    <Button
            android:layout_width="100dp"
            android:layout_height="0dp"
            android:text="5. DimensionRatio"
            app:layout_constraintDimensionRatio="1:1.5"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintTop_toTopOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintVertical_bias="0.296"
            app:layout_constraintHorizontal_bias="0.051"/>
~~~


6. GuideLine
화면설계에 도움되는 것. 실제로는 안보임. horizontal, vertical이 반대임. 세밀한 화면을 설계할 것이라면 사용하기를 권장함. 

~~~xml
<!--horizontal, vertical이 반대임-->
    <!--horizontal, end-->
    <android.support.constraint.Guideline
            android:orientation="horizontal"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:layout_constraintGuide_end="165dp"
            android:id="@+id/guideline1"/>

    <!--vertical, begin-->
    <android.support.constraint.Guideline
            android:orientation="vertical"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:layout_constraintGuide_begin="202dp"
            android:id="@+id/guideline2"/>

    <!--horizontal, begin-->
    <android.support.constraint.Guideline
            android:orientation="horizontal"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:layout_constraintGuide_begin="365dp"
            android:id="@+id/guideline3"/>

    <!--percent 0.8-->
    <android.support.constraint.Guideline
            android:orientation="vertical"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:layout_constraintGuide_percent="0.8"
            android:id="@+id/guideline4"/>
~~~
