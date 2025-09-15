
📦 Full repo: [commerce-platform-fullstack-Dacodes](https://github.com/GregHowe/commerce-platform-fullstack-Dacodes/tree/main/Core.Builder)

Core.Builder is the user-facing application of the Core system, and allows clients to author compliant sites, with automatic deployment:

<br>
📦 Schema-Driven Rendering You're using v-for to iterate over schemaFields and dynamically generate v-select inputs. This pattern is powerful for building configurable UIs — especially in admin panels or CMS-like tools.
<br><br>
Vuex Integration The use of mapState to pull fieldSchema and schemaFields from the store shows you're centralizing state and avoiding prop drilling. That’s a sign of scalable frontend architecture.
<br><br>
Vuetify Layout Leveraging v-row and v-col gives you responsive, grid-based layout out of the box. It’s clean, declarative, and visually consistent.
<br><br>
Show how you conditionally render components based on conditionals
<br><br>
<img width="660" height="984" alt="image" src="https://github.com/user-attachments/assets/4aa43abf-305a-45b9-86c4-396b1011b2f4" />


<br><br>
📦 Modular Vuex Design The use of state, mutations, and actions in a dedicated brand.js file shows you're following Vuex best practices. It keeps the store maintainable and scalable.<br><br>
Async-Aware Action (loadBrand) You're fetching brand data via Axios and committing it to state — a clean separation of side effects and state mutation. This is ideal for onboarding flows or tenant-specific branding.

<br>
<img width="449" height="683" alt="image" src="https://github.com/user-attachments/assets/54bbbe4a-bb01-47dc-803e-de98ecb3f278" />

<br><br>
📦 This component manages a custom loading indicator for Nuxt page transitions and async operations. It supports granular control over animation state, success/failure feedback, and lifecycle cleanup — enhancing perceived performance and user trust.
Lifecycle Awareness The use of beforeDestroy ensures cleanup — a sign of disciplined component lifecycle management.
<img width="738" height="991" alt="image" src="https://github.com/user-attachments/assets/24ba54d9-36e8-4344-a194-bcf3d59c40ed" />
