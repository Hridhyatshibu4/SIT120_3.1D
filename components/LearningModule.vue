<template>
  <div class="learning-module">
    <h2>Learning Module</h2>

    <!-- Video Lectures -->
    <div class="lecture-list">
      <h3>Video Lectures</h3>
      <ul>
        <li v-for="(lecture, index) in videoLectures" :key="index">
          <!-- Check if the media type is video -->
          <template v-if="isVideo(lecture.url)">
            <!-- Display Deakin video URLs as links -->
            <a :href="lecture.url" target="_blank">{{ lecture.title }}</a>
          </template>
          <!-- Check if the media type is YouTube -->
          <template v-else-if="isYouTube(lecture.url)">
            <iframe width="480" height="270" :src="embedYouTube(lecture.url)" frameborder="0" allowfullscreen></iframe>
          </template>
          <!-- If it's not video or YouTube, treat it as a link -->
          <template v-else>
            <a :href="lecture.url" target="_blank">{{ lecture.title }}</a>
          </template>
        </li>
      </ul>
    </div>

    <!-- One line space -->
    <div class="spacer"></div>

    <!-- YouTube Video -->
    <div class="youtube-video">
      <h3>YouTube Video</h3>
      <iframe width="480" height="270" :src="embedYouTube('https://youtu.be/VpB0eVZir8U?si=rPWaKuc_NsHFfTFo')" frameborder="0" allowfullscreen></iframe>
    </div>

    <!-- Add your three videos from assets -->
    <div class="asset-videos">
      <h3>Asset Videos</h3>
      <ul>
        <!-- You can add more videos here as needed -->
        <li class="video-item">
          <video controls height="240" width="480">
            <source src="@/assets/Video1.mp4" type="video/mp4">
            Your browser does not support the video element.
          </video>
        </li>
        <li class="video-item">
          <video controls height="240" width="480">
            <source src="@/assets/Video2.mp4" type="video/mp4">
            Your browser does not support the video element.
          </video>
        </li>
        <li class="video-item">
          <video controls height="240" width="480">
            <source src="@/assets/Video3.mp4" type="video/mp4">
            Your browser does not support the video element.
          </video>
        </li>
      </ul>
    </div>

    <!-- Audio Links -->
    <div class="audio-list">
      <h3>Audio Links</h3>
      <ul>
        <li v-for="(audio, index) in audioLinks" :key="index">
          <!-- Check if the media type is audio -->
          <template v-if="isAudio(audio)">
            <audio controls>
              <source :src="getAudioUrl(audio)" type="audio/mpeg">
              Your browser does not support the audio element.
            </audio>
          </template>
          <!-- If it's not audio, treat it as a regular link -->
          <template v-else>
            <a :href="getAudioUrl(audio)" target="_blank">{{ audio }}</a>
          </template>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LearningModule',
  data() {
    return {
      videoLectures: [
        { title: 'Video Lecture 1', url: 'https://video.deakin.edu.au/media/t/1_1wmqj0vn' },
        
        { title: 'Video Lecture 2', url: 'https://video.deakin.edu.au/media/t/1_59br1ksh' },
        { title: 'Video Lecture 3', url: 'https://video.deakin.edu.au/media/t/1_wpil7rdw' },
      
      ],
      audioLinks: ['audio1'],
    };
  },
  methods: {
    getAudioUrl(audioName) {
      return require(`@/assets/${audioName}.mp3`);
    },
    isVideo(url) {
      // Check if the URL is a video URL (you can add more video sources as needed)
      return url.includes('video.deakin.edu.au') || url.includes('vimeo.com');
    },
    isYouTube(url) {
      // Check if the URL is a YouTube URL
      return url.includes('youtube.com') || url.includes('youtu.be');
    },
    embedYouTube(url) {
      // Get the YouTube embed URL from a regular YouTube URL
      if (url.includes('youtube.com')) {
        const videoId = url.split('v=')[1];
        return `https://www.youtube.com/embed/${videoId}`;
      } else if (url.includes('youtu.be')) {
        const videoId = url.split('/').pop();
        return `https://www.youtube.com/embed/${videoId}`;
      }
      return url;
    },
    isAudio(audioName) {
      // You can add more audio file extensions if needed
      return audioName.endsWith('.mp3');
    },
  },
};
</script>

<style scoped>
/* Add your CSS styles for the learning module here */
/* Style for embedded videos */
iframe {
  width: 80%;
  height: 350px; /* Adjust the height as needed */
}

/* Style for asset videos */
.asset-videos video {
  width: 80%;
  max-height: 400px; /* Adjust the max height as needed */
}

/* Add spacing between videos */
.video-item {
  margin-bottom: 20px;
}

/* Add spacing between video lectures and YouTube video */
.spacer {
  height: 20px;
}
</style>
