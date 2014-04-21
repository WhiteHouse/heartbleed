Heartbleed
==========

This module was developed in response to the Heartbleed bug in OpenSSL.

The problem Heartbleed module solves is this: I need my Drupal site users to
reset their passwords. I don't have any reason to believe passwords were
compromised, and I don't want to alarm anyone. But I don't want people to be
able to keep using passwords that may have potentially been compromised.

Here's the user experience for an authenticated users on example.com after Heartbleed
module is installed:

 - (I remember my password.) Next time I log into example.com, I'm immediately
   logged back out and sent to example.com/user/heartbleed. Here I see a note
   informing me about Heartbleed and instructing me to enter my email address to
   request a password reset link be sent to my email.
 - (I forgot my password.) Nothing changes. When I go to example.com to log in,
   I request a login link to be sent to my email. When I use it to reset my
   password, Heartbleed checks me off the list of users who need to reset their
   passwords. I may never know about or worry about Heartbleed impacting me on
   example.com.

Here are some sites with information about the Heartbleed bug in OpenSSL:
 - http://heartbleed.com/
 - http://www.dhs.gov/stopthinkconnect-heartbleed


Install & Configure
-------------------

 1. Download Heartbleed module.

 2. Drop it in your Drupal site's sites/all/modules directory.

 3. Enable Heartbleed module here:

        admin/build/modules (Drupal 6)
        admin/modules       (Drupal 7)
 
 4. Customize Heartbleed settings here:

        admin/user/heartbleed          (Drupal 6)
        admin/config/people/heartbleed (Drupal 7)

      **Password reset date**: All users created before the reset date
      will be required to change their password once after the reset date. (If
      you change the date after the module is enabled, password resets that
      happened before the new date won't count. Users will have to reset their
      passwords again.)

      **Heartbleed message**: Customize the message displayed to your users about
      why they are being required to reset their passwords.
