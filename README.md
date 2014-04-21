Heartbleed
==========

This module was developed in response to the Heartbleed bug in OpenSSL.

The problem Heartbleed module solves is this: I have patched my site against the Heartbleed vulnerability, 
and I want my Drupal site users to reset their passwords. There's no indication Heartbleed was used against my site, but out of an abundance of caution I want to reset all of my users' passwords to ensure their protection.

Here's the user experience for an authenticated user on example.com after Heartbleed
module is installed:

 - (I remember my password.) Next time I log into example.com, I'm immediately
   logged out and redirected to example.com/user/heartbleed. Here I see a note
   informing me about Heartbleed and instructing me to enter my email address to
   request a password reset link be sent to my email.
 - (I forgot my password.) Nothing changes. When I go to example.com to log in,
   I request a login link to be sent to my email. When I use it to reset my
   password, Heartbleed checks me off the list of users who need to reset their
   passwords. I may never know about or worry about Heartbleed impacting me on
   example.com.

Here are some sites with information about the Heartbleed bug in OpenSSL:
 - http://www.dhs.gov/stopthinkconnect-heartbleed
 - http://heartbleed.com/


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
