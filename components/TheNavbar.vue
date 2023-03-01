<template>
  <div >
    <div class="flex justify-between items-center pb-2">
      <div class="flex space-x-1">
        <span class="text-secondary">
          <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" height="80px" width="150px" xmlns="http://www.w3.org/2000/svg"><g><path fill="none" d="M0 0h24v24H0z"></path><path d="M3 3h18a1 1 0 0 1 1 1v16a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V4a1 1 0 0 1 1-1zm13.464 12.536L20 12l-3.536-3.536L15.05 9.88 17.172 12l-2.122 2.121 1.414 1.415zM6.828 12L8.95 9.879 7.536 8.464 4 12l3.536 3.536L8.95 14.12 6.828 12zm4.416 5l3.64-10h-2.128l-3.64 10h2.128z"></path></g></svg>
        </span>
      </div>
      <div class="flex space-x-2 items-center">
        <SearchBar />
        <button
          class="border border-secondary bg-secondary font-semibold px-3 py-2 shadow rounded-md  hover:opacity-70 transition-all duration-200"
        >
          Add your portfolio
        </button>
      </div>
    </div>
    <hr>
  </div>
</template>

<script>
export default {}
</script>

<style scoped></style>
