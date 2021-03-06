.. _usage:

Usage
=====

Integrating `kaleo` into your project is just a matter of using a couple of
template tags and wiring up a bit of javascript. The invite form is intended
to function via AJAX and as such returns JSON.

Firstly, you will want to add the following blocks in your templates where
you want to expose the invite form and display to the user a list of who they
have invited (of course you may choose to not expose that)::

    {% load kaleo_tags %}
    
    <div class="invites">
        {% invite_form request.user %}
        
        <div class="sent">
            <h3>Invitations Sent</h3>
            {% invites_sent request.user %}
        </div>
    </div>


Then if you had an account bar somewhere at the top of your screen where you
showed the user if they were logged in or note you could have::

    {% load kaleo_tags %}
    
    {% invites_remaining user %}


You'll then need to include bootstrap-ajax::

    <script src="{% static "js/bootstrap-ajax.js" %}"></script>
