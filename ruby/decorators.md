# Using Decorators

## With Devise - adding decorator to current_user
- Using Draper, Decorators allow you to move view related functionality for your models in to separate decorator classes. Benefit = models and views clean and readable.

When using Devise you have a current_user helper which is nice. However, the helper returns an instance of User without our decorators. In order to enable our decorators by default with current_user just add this to app/controllers/application_controller.rb
ex:

def current_user
  UserDecorator.decorate(super) unless super.nil?
end

(unless super.nil prevents 'user_signed_in?' from always returning true.)

Now, anywhere in your views where we call current_user we'll get a decorated version instead.
