# Commit mesajı nasıl olmalıdır?

```
DEV-12 #time 25m #comment Do not send email at staging env.

We should never accidentally send emails to real people from your
staging environment.

- Send all email to noreply@domain.com
- Implement recipient_interceptor gem

```

* Mutlaka ingilizce olmalıdır.
* Mutlaka Jira iş numarası ile ilişkilendirilmelidir.
* Mutlaka harcanan süre belirtilmelidir.
* Mutlaka başlık 50 satırı geçmemelidir ve büyük harf ile başlamalıdır.
* Gerekirse bir boşluk bırakıldıktan sonra 72 karakteri geçmeyecek şekilde daha detaylı bir bilgi verilmelidir.

**Kaynaklar**

* http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
* https://github.com/torvalds/linux/pull/17#issuecomment-5659933
