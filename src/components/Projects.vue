<template>
  <section id="github" class="github">
    <div class="container-git">
        <!-- PROFILE CARD -->
        <div class="profile-card" v-if="user">

        <img :src="user.avatar_url" alt="avatar" />

        <div class="profile-info">
            <h2>{{ user.name || user.login }}</h2>
            <span class="role">Software Engineer</span>

            <p class="bio">
            {{ user.bio || 'Building scalable web applications' }}
            </p>

            <div class="stats">
            <div>
                <strong>{{ user.followers }}</strong>
                <span>Followers</span>
            </div>

            <div>
                <strong>{{ user.public_repos }}</strong>
                <span>Repos</span>
            </div>

            <div>
                <strong>{{ totalStars }}</strong>
                <span>Stars</span>
            </div>
            </div>
        </div>

        </div>
        <!-- REPOS -->
        <div class="repos" v-if="repos.length">
        <h3>Repositórios recentes</h3>
        <div
            v-for="repo in repos.slice(0, 5)"
            :key="repo.id"
            class="repo"
        >
            <a :href="repo.html_url" target="_blank">
            📦 {{ repo.name }}
            </a>

            <div class="repo-meta">
            ⭐ {{ repo.stargazers_count }}
            🍴 {{ repo.forks_count }}
            </div>
        </div>
        </div>
    </div>
  </section>
</template>

<script setup>
    import { ref, onMounted } from 'vue'

    const username = ref('kadutec')

    const user = ref(null)
    const repos = ref([])
    const totalStars = ref(0)

    const loadData = async () => {

    const userRes = await fetch(`https://api.github.com/users/${username.value}`)
    user.value = await userRes.json()

    const repoRes = await fetch(`https://api.github.com/users/${username.value}/repos?sort=updated`)
    repos.value = await repoRes.json()

    totalStars.value = repos.value.reduce(
        (acc, repo) => acc + repo.stargazers_count,
        0
    )
    }

    onMounted(loadData)
</script>