# FullCalendar
See the [FullCalendar Docs](https://fullcalendar.io/) for more details  
(개인적으로는 docs에서 필요한 기능을 찾는 것보다 키워드로 구글링하는 게 접근이 편했다)

## Calendar.vue

### in template
```html
<FullCalendar
    :options="calendarOptions"
    ref="calendar"
/>
```

### in script
```javascript
import FullCalendar from '@fullcalendar/vue'
import dayGridPlugin from '@fullcalendar/daygrid'
import timeGridPlugin from '@fullcalendar/timegrid'

data() {
    calendarOptions: {
        plugins: [ dayGridPlugin, timeGridPlugin ],
        initialView: 'dayGridMonth',
        // width가 height의 두 배
        aspectRatio: 2,
         // header를 custom 개발해서 사용했다.
        headerToolbar: false,
    
        // dayGrid
        // 이번 년도 몇 번째 주인지 표시 여부
        fixedWeekCount: false,
        // Month 캘린더에 maximum 몇 개의 일정을 표시할 것인지 (그 이상은 more로 표시)
        dayMaxEvents: 2,
    
        // timeGrid
        // 현재 시간 표시
        nowIndicator: true,
        // 해당 일에 모든 일정 한 눈에 보기
        allDaySlot: false,
        // 일정 겹쳐서 표시하기
        slotEventOverlap: false,
        // 초기 스크롤의 위치
        scrollTime: '09:00:00',
        // 시간 표시 간격
        slotDuration: '01:00:00',
        // 시간 표시 포맷
        slotLabelFormat: {
            hour: 'numeric',
            minute: '2-digit',
            omitZeroMinute: false,
            meridiem: 'long' // 'short'하면 소문자 am/pm
        },
    
        // custom
        // more 클릭 시 이벤트
        moreLinkClick: this.onClickMoreLink,
        // 일정 내용(Title) 커스텀 (v-slot으로 대체 가능)
        eventContent: this.eventContentFormatter,
        // more 라벨 내용 커스텀 (v-slot으로 대체 가능)
        moreLinkContent: this.moreLinkContentFormatter,
        // Month 캘린더의 Day Cell 커스텀 (v-slot으로 대체 가능)
        dayCellContent: this.dayCellContentFormatter,
        // Day 캘린더의 Header 커스텀 (v-slot으로 대체 가능)
        dayHeaderContent: this.dayHeaderContentFormatter,
        // Day 캘린더의 시간 표시 내용 커스텀 (v-slot으로 대체 가능)
        slotLabelContent: this.slotLabelContentFormatter,
        // 일정
        /** @type {Array.<CalendarEvent>} */ events: [],
    },
}
methods: {
    /**
     * @return {String|Object|Function} 
     *  - Object는 { html: '<div> Content </div>' } 포맷을 사용했다.
     */
    onClickMoreLink(args) {},
    eventContentFormatter(args) {},
    moreLinkContentFormatter(args) {},
    dayCellContentFormatter(args) {},
    dayHeaderContentFormatter(args) {}
    slotLabelContentFormatter(args) {}
}
```

### jsDoc
```javascript
/**
* @typedef {Object} CalendarEvent
* @property {String} title
* @property {Date|String} start
*  - string일 경우 'yyyy-MM-dd hh:mm:ss'
* @property {Date|String} end
*  - string일 경우 'yyyy-MM-dd hh:mm:ss'
*/
```