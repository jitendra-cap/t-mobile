<script setup>
import { ref, computed, onMounted } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import Left from './../../assets/icon/icon-chevron-Left.png'
import Right from './../../assets/icon/icon-chevron-Right.png'
import Down from './../../assets/icon/icon-chevron-down-small.png'
import holidayIcon from './../../assets/icon/IconButton.png'
import './managerWeeklySchedule.scss'

const tableHeight = ref(0)
const calendarTable = ref(null)

const cssVars = computed(() => {
  return {
    '--height': `${tableHeight.value}px`
  }
})

onMounted(() => {
  //update the height value of the active column
  tableHeight.value = calendarTable.value.clientHeight
})
</script>

<template>
  <div class="tmobile-msws">
    <div class="tmobile-msws__title">
      <div class="tmobile-msws__title-heading">
        My Team`s Weekly Schedule <br />
        <h4>All Times are Local</h4>
      </div>
      <div class="tmobile-msws__title-back"><u>UKG Pro —></u></div>
    </div>

    <div class="tmobile-msws__subheading">
      <div class="tmobile-msws__subheading__ds">Daily Schedule</div>
      <div class="tmobile-msws__subheading__ws">Weekly Schedule</div>
    </div>

    <div class="tmobile-msws__date-selector">
      <div class="tmobile-msws__date-selector-detail">
        <span class="icon-outer">
          <img :src="Left" class="icon" />
          &nbsp; June 1 - June 7 &nbsp;
          <img :src="Right" class="icon" />
        </span>
      </div>
      <div class="tmobile-msws__date-selector-event">
        <span class="icon-outer">
          San Mateo #245 &nbsp;
          <img :src="Down" class="icon" />
        </span>
      </div>
    </div>

    <div class="tmobile-msws__body">
      <div class="tmobile-msws__body-container">
        <div class="tmobile-msws__body-container-calendar">
          <table class="tmobile-msws__body-container-calendar__calendar-view" ref="calendarTable">
            <thead>
              <tr class="tmobile-msws__body-container-calendar__calendar-view__head">
                <th>Employees</th>
                <th>SUN <span class="date">01</span></th>
                <th>MON <span class="date">02</span></th>
                <th>TUE <span class="date">03</span></th>
                <th id="activeColumn" class="active-column" :style="cssVars">
                  WED <span class="date">04</span>
                </th>
                <th>
                  <span class="holiday"
                    >THU <span class="date">&nbsp;05 </span>
                    <img class="holiday-icon" :src="holidayIcon"
                  /></span>
                </th>
                <th>FRI <span class="date">06</span></th>
                <th>SAT <span class="date">07</span></th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td colspan="8" class="emp-group">ASSISTENT MANAGER</td>
              </tr>

              <tr class="emp-row">
                <td>Kai Thompson</td>
                <td class="full-availability"></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td><span class="shift-another-location">OTHER LOC</span></td>
                <td></td>
              </tr>
              <tr class="emp-row">
                <td style="text-align: left">Kai Thompson</td>
                <td></td>
                <td class="not-scheduled">
                  <div class="not-scheduled-inner"></div>
                </td>
                <td></td>
                <td>
                  <span class="shift-another-location">OTHER LOC</span>
                  <span class="shift-another-location">OTHER LOC</span>
                  <span class="shift-another-location">OTHER LOC</span>
                </td>
                <td class="partial-availability">
                  <span class="long-timing-tag">08AM - 03PM</span>
                </td>
                <td></td>
                <td></td>
              </tr>

              <tr>
                <td class="emp-group" colspan="8">SALES REPRESENTIVE</td>
              </tr>

              <tr class="emp-row">
                <td>Kai Thompson</td>
                <td>
                  <a class="anchor" href="#"> <span class="short-timing-tag">08AM - 03PM</span></a>
                  <a class="anchor" href="#">
                    <span class="long-timing-tag">08AM - 03PM</span>
                  </a>
                </td>
                <td>
                  <a class="anchor" href="#">
                    <span class="exception-tag">*EXCP</span>
                  </a>
                </td>
                <td></td>
                <td></td>
                <td></td>
                <td>
                  <a class="anchor" href="#"><span class="short-timing-tag">08AM - 03PM</span></a>
                  <a class="anchor" href="#">
                    <span class="long-timing-tag">08AM - 03PM</span>
                  </a>
                </td>
                <td></td>
              </tr>
              <tr class="emp-row">
                <td>Kai Thompson</td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td>
                  <a class="anchor" href="#"><span class="short-timing-tag">08AM - 03PM</span></a>
                  <a class="anchor" href="#">
                    <span class="long-timing-tag">08AM - 03PM</span>
                  </a>
                </td>
                <td></td>
              </tr>
              <tr class="emp-row">
                <td>Kai Thompson</td>
                <td></td>
                <td></td>
                <td></td>
                <td>
                  <a class="anchor" href="#"><span class="short-timing-tag">08AM - 03PM</span></a>
                  <a class="anchor" href="#">
                    <span class="long-timing-tag">08AM - 03PM</span>
                  </a>
                </td>
                <td></td>
                <td></td>
                <td></td>
              </tr>
              <tr>
                <td class="emp-group" colspan="8">CUSTOMER CARE</td>
              </tr>
              <tr class="emp-row">
                <td>Kai Thompson</td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td>
                  <a class="anchor" href="#"><span class="short-timing-tag">08AM - 03PM</span></a>
                  <a class="anchor" href="#">
                    <span class="long-timing-tag">08AM - 03PM</span>
                  </a>
                  <a class="anchor" href="#">
                    <span class="long-timing-tag">08AM - 03PM</span>
                  </a>
                  <a class="anchor" href="#">
                    <span class="long-timing-tag">08AM - 03PM</span>
                  </a>
                </td>
                <td></td>
              </tr>
              <tr class="emp-row">
                <td>Kai Thompson</td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
              </tr>
            </tbody>
          </table>
        </div>
        <!---Hint section start-->
        <div class="tmobile-msws__body-container__hint">
          <table class="tmobile-msws__body-container__hint-section">
            <tr>
              <td><span class="short-timing-tag">XX XX - XX XX</span></td>
              <td>Short Shift</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>

              <td><span class="exception-tag">*EXCP</span></td>
              <td>Exception</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>

              <td>
                <div style="margin-top: -10px" class="full-availability"></div>
              </td>
              <td>Full Availability</td>
              <td rowspan="2">&nbsp; &nbsp; &nbsp; &nbsp;</td>

              <td rowspan="2">
                <div class="not-scheduled" style="padding: 30px">
                  <div class="not-scheduled-inner"></div>
                </div>
              </td>
              <td>Not Scheduled</td>
            </tr>
            <tr>
              <td><span class="hint_long-timing">XX XX - XX XX</span></td>
              <td>Long Shift</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>

              <td><span class="shift-another-location">Other LOC</span></td>
              <td>Shift Another Location</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
              <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
              <td>
                <div style="margin-top: -10px" class="partial-availability"></div>
              </td>
              <td>Partial Availability</td>
            </tr>
          </table>
        </div>
        <!---Hint section Esnd-->
      </div>
    </div>
  </div>
</template>
