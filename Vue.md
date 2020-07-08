# Vue JS

### 단축어
* `#` (v-slot)
    ```html
    <BDropdown
        size="sm"
        no-caret
    >
        <template #button-content> <!-- v-slot: -->
            <FontAwesomeIcon icon="bars" />
        </template>
        <BDropdownItem .../>
    </BDropdown>
    ```
* `:` (v-bind)
    ```html
    <Component :is="activeMenu" /> <!-- v-bind -->
    ```
* `@` (v-on)
    ```html
    <BButton
        size="sm"
        variant="info"
        @click="clickAction()"
    >
        <FontAwesomeIcon icon="search" /> <!-- v-on -->
    </BButton>
    ```
