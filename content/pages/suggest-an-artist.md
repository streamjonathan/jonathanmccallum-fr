---
title: "Proposer un artiste"
slug: suggest-an-artist
---

J'adore découvrir des musiciens et des artistes qui suivent Jésus. Si vous connaissez quelqu'un dont je devrais parler, que je devrais interviewer ou sur qui je devrais faire une vidéo réaction, dites-le-moi ici.

Un nom et un lien suffisent — et quelques mots sur pourquoi cette personne. Je lis tout ce qui arrive. Merci beaucoup.

Vous connaissez quelqu'un ? Touchez sa photo et le formulaire se remplit tout seul — puis ajoutez quelques mots sur pourquoi cette personne et envoyez.

<div class="suggest-carousel" role="list" aria-label="Musiciens et artistes que vous pouvez proposer">
{% for artist in suggest_carousel %}
  <button type="button" class="suggest-pick" role="listitem" data-artist="{{ artist.name }}" data-link="{{ artist.profile }}" title="Proposer {{ artist.name }}">
    <img src="{{ artist.img }}" alt="{{ artist.name }}" loading="lazy" width="150" height="150">
    <span class="suggest-pick__name">{{ artist.name }}</span>
    <span class="suggest-pick__note">{{ artist.note }}</span>
  </button>
{% endfor %}
</div>

<p class="suggest-carousel__more">Ou proposez quelqu'un de nouveau ci-dessous — toute personne dont vous pensez que je devrais entendre parler.</p>

Ce site n'est pas destiné aux personnes de moins de 18 ans.

<form id="suggest-form" class="suggest-form">
  <label for="suggest-artist">Nom de l'artiste</label>
  <input id="suggest-artist" name="artist" type="text" maxlength="200" placeholder="Qui devrais-je découvrir ?" required>

  <label for="suggest-link">Lien vers son profil sur les réseaux sociaux</label>
  <input id="suggest-link" name="link" type="url" maxlength="500" placeholder="https://www.instagram.com/…" required>

  <fieldset class="suggest-kinds">
    <legend>Qu'est-ce que je fais avec cette personne ?</legend>
    <label><input type="checkbox" name="kind" value="write"> Parler de cette personne</label>
    <label><input type="checkbox" name="kind" value="interview"> Interviewer cette personne</label>
    <label><input type="checkbox" name="kind" value="reaction"> Faire une vidéo réaction sur cette personne</label>
  </fieldset>

  <label for="suggest-why">Pourquoi cette personne ?</label>
  <textarea id="suggest-why" name="why" rows="3" maxlength="500" placeholder="Quelques mots suffisent…"></textarea>

  <label for="suggest-name">Votre nom <span class="optional">(facultatif)</span></label>
  <input id="suggest-name" name="fromName" type="text" maxlength="100" placeholder="Pour que je puisse vous remercier">

  <label for="suggest-from-link">Lien vers votre profil sur les réseaux sociaux <span class="optional">(facultatif)</span></label>
  <input id="suggest-from-link" name="fromLink" type="url" maxlength="500" placeholder="https://www.instagram.com/…">

  <button id="suggest-button" type="button">Envoyer la proposition</button>

  <p id="suggest-result" aria-live="polite"></p>
</form>
