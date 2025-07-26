<script setup>
import { themeColor } from "../data/items";
import mainPhoto from "../assets/images/about.svg";

const heading = "About";
const subHeading = "What's the Deal with Us?";
const totalMembers = "100";
const totalTeam = "40";
</script>

<template>
  <div class="untree_co-section" id="about-section">
    <div class="container">
      <div class="row justify-content-between">
        <div class="col-lg-8" data-aos="fade-up" data-aos-delay="100">
          <img :src="mainPhoto" alt="Image" class="img-fluid" />
        </div>
        <div class="col-lg-4">
          <div class="mb-4" data-aos="fade-up" data-aos-delay="0">
            <span class="caption" :style="[{ color: themeColor }]">{{
              heading
            }}</span>
            <h2 class="heading">{{ subHeading }}</h2>
          </div>
          <div class="mb-4" data-aos="fade-up" data-aos-delay="100">
            <p>
              So we're sitting around the office, right? And somebody says, 
              "Hey, what if we actually tried to be good at what we do?" 
              I mean, what kind of crazy idea is that? But here we are!
            </p>
            <p>
              You know what I love about our team? 
              <span class="highlight">
                We're like a sitcom about nothing, except we actually get things done
              </span>. 
              It's like we took all the neuroses, the obsessing over details, 
              the endless conversations about the proper way to organize a desk - 
              and somehow turned it into a business.
            </p>
          </div>
          <ul
            class="list-unstyled ul-check primary mb-4"
            data-aos="fade-up"
            data-aos-delay="200"
          >
            <li>We argue about everything (it's productive, we swear)</li>
            <li>No soup for bad code</li>
            <li>Yada yada yada... success!</li>
          </ul>
          <div class="row count-numbers">
            <div class="col-lg-6" data-aos="fade-up" data-aos-delay="0">
              <span class="counter d-block"
                ><span :data-number="totalMembers">{{ totalMembers }}</span
                ><span>M</span></span
              >
              <span class="caption-2">Members</span>
            </div>
            <div class="col-lg-6" data-aos="fade-up" data-aos-delay="100">
              <span class="counter d-block"
                ><span :data-number="totalTeam">{{ totalTeam }}</span
                ><span></span
              ></span>
              <span class="caption-2">Team</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
