---
apple-notes-id: DF6A5D98-5413-4D02-8E01-C41429452237
---
1.7747529999760445\]
 test_should_display_user_when_activated#UserShowTest (1.77s)
ActionView::**Template::Error**:         ActionView::Template::Error: undefined method `**following**?' for nil:NilClass
            app/views/users/_follow_form.html.erb:3
            app/views/users/show.html.erb:15
            test/integration/user_show_test.rb:17:in `block in <class:UserShowTest>'

ERROR\["test_micropost_interface",
 #<Minitest::Reporters::Suite:0x00007faf9976d900 @name="MicropostsInterfaceTest">, 2.2949030000017956\]
 test_micropost_interface#MicropostsInterfaceTest (2.29s)
ActionView::**Template::Error**:         ActionView::Template::Error: undefined method `**following?**' for #<User:0x00007faf9df71d78>
        Did you mean?  following
                       folowing?
                       following=
            app/views/users/_follow_form.html.erb:3
            app/views/users/show.html.erb:15
            test/integration/microposts_interface_test.rb:35:in `block in <class:MicropostsInterfaceTest>'

ERROR\["test_profile_display", #<Minitest::Reporters::Suite:0x00007faf99268e00 @name="UsersProfileTest">, 3.0245149999973364\]
 test_profile_display#UsersProfileTest (3.02s)
ActionView::**Template::Error**:         ActionView::Template::Error: undefined method `**following?'** for nil:NilClass
            app/views/users/_follow_form.html.erb:3
            app/views/users/show.html.erb:15
            test/integration/users_profile_test.rb:11:in `block in <class:UsersProfileTest>'

ERROR\["test_user_follow/unfollow_another_user", #<Minitest::Reporters::Suite:0x00007faf95c00b10 @name="UserTest">, 3.272503999993205\]
 test_user_follow/unfollow_another_user#UserTest (3.27s)
NoMethodError:         **NoMethodError**: undefined method `**following?**' for #<User:0x00007faf9db87938>
            test/models/user_test.rb:90:in `block in <class:UserTest>'