<template>
  <div class="container mt-5">
    <!-- Main Box -->
    <div class="custom-box">
      <!-- Header (Tag Details with Icon - No Background) -->
      <div class="header-container">
        <i class="bi bi-tag"></i>
        <h6 class="text-primary m-0">Tag Details</h6>
      </div>

      <!-- Close Button (Above Edit Button) -->
      <button type="button" class="btn-close" aria-label="Close" @click="closeTag"></button>

      <!-- "Roaa Tag" with Icon + "Edit Tag Information" on the Same Line (No Background) -->
      <div class="title-row">
        <div class="title-container">
          <i class="bi bi-tag"></i>
          <h4 class="custom-title">Roaa Tag</h4>
        </div>
        <button class="btn btn-outline-secondary btn-sm" @click="editTag">Edit tag information →</button>
      </div>

      <!-- Content Box (Background Starts Here) -->
      <div class="content-box">
        <!-- Tag Name and Created Date -->
        <div class="row">
          <div class="col-md-6">
            <small class="text-muted">Tag Name</small>
            <p class="fw-bold">Roaa Tag</p>
          </div>
          <div class="col-md-6">
            <small class="text-muted">Created Date</small>
            <p class="fw-bold">2023-11-06 14:44:32</p>
          </div>
        </div>
        <div class="divider"></div>

        <!-- Accounts -->
        <div>
          <small class="text-muted">Accounts</small>
          <p><span class="badge badge-custom">Roaa Sawalmeh</span></p>
        </div>
        <div class="divider"></div>

        <!-- Units -->
        <div>
          <small class="text-muted">Units</small>
          <div>
            <span v-for="(unit, index) in units" :key="'unit'+index" class="badge badge-custom">{{ unit }}</span>
          </div>
        </div>
        <div class="divider"></div>

        <!-- Drivers -->
        <div>
          <small class="text-muted">Drivers</small>
          <div>
            <span v-for="(driver, index) in drivers" :key="'driver'+index" class="badge badge-custom">{{ driver }}</span>
          </div>
        </div>
        <div class="divider"></div>

        <!-- Areas -->
        <div>
          <small class="text-muted">Areas</small>
          <div>
            <span v-for="(area, index) in areas" :key="'area'+index" class="badge badge-custom">{{ area }}</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Close Button -->
    <div class="text-center mt-4">
      <button class="btn btn-light w-100" @click="closeTag">Close</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TagDetails',
  data() {
    return {
      units: [
        'Aljaber',
        '518 مرسيدس',
        'Sprinter-1249',
        '2512 - بوكس',
        '1702 كادي',
        'Test Car',
        'الفيوكو ديلي',
        'إسوزو',
        '1568 التكو',
        '5160 مترسيبشي',
        '0054 - سيارات'
      ],
      drivers: [
        'Firas Shaarawi',
        'Ashraf Skaffi',
        'Ahmad',
        'Ahmad',
        'Driver1',
        'Tawfiq1'
      ],
      areas: [
        'Test####',
        'وكالة موئنان',
        'Test Test',
        'Roaa Test',
        'New Test'
      ]
    }
  },
  methods: {
    closeTag() {
      // Emit event to parent or handle close logic
      this.$emit('close');
    },
    editTag() {
      // Handle edit logic
      this.$emit('edit');
    }
  }
}
</script>

<style scoped>
/* Centering the Main Box */
.container {
  max-width: 600px; /* Fixed width */
  margin: auto; /* Center horizontally */
}

/* Main Box (Only White Background) */
.custom-box {
  border-radius: 10px;
  padding: 20px;
  position: relative;
  border: 1px solid #DEE2E6;
}

/* Header (Tag Details - No Background) */
.header-container, .title-container {
  display: flex;
  align-items: center;
  gap: 5px; /* Space between icon and text */
}

/* "Roaa Tag" and "Edit" in Same Line (No Background) */
.title-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

/* Title Styling */
.custom-title {
  display: flex;
  align-items: center;
  font-weight: bold;
  font-size: 20px;
  margin: 0;
  gap: 5px; /* Space between icon and text */
}

/* Content Box (Now has Background) */
.content-box {
  background-color: #F8F9FA;
  padding: 20px;
  border-radius: 10px;
  border: 1px solid #DEE2E6;
}

/* Badges */
.badge-custom {
  background-color: #0000A0;
  color: white;
  padding: 8px 12px;
  border-radius: 6px;
  margin: 2px;
  display: inline-block;
}

/* Divider */
.divider {
  border-top: 1px solid #DEE2E6;
  margin: 10px 0;
}

/* Close Button */
.btn-close {
  position: absolute;
  top: 15px;
  right: 15px;
}
</style>