<script setup>
import { ref, computed, onMounted } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
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
      <div class="tmobile-msws__title__heading">
        My Team`s Weekly Schedule <br />
        <h4>All Times are Local</h4>
      </div>
      <div class="tmobile-msws__title__back">
        <a class="anchor" href="#">UKG Pro <font-awesome-icon icon="arrow-right" class="icon" /></a>
      </div>
    </div>

    <div class="tmobile-msws__subheading">
      <div class="tmobile-msws__subheading__borderless">Daily Schedule</div>
      <div class="tmobile-msws__subheading__border"><a>Weekly Schedule</a></div>
    </div>

    <div class="tmobile-msws__calendar">
      <div class="tmobile-msws__calendar__detail">
        <span class="icon-outer">
          <font-awesome-icon icon="chevron-left" class="icon" />
          &nbsp; June 1 - June 7 &nbsp;
          <font-awesome-icon icon="chevron-right" class="icon" />
        </span>
      </div>
      <div class="tmobile-msws__calendar__event">
        <span class="icon-outer">
          San Mateo #245 &nbsp;
          <font-awesome-icon icon="chevron-down" class="icon" />
        </span>
      </div>
    </div>

    <div class="tmobile-msws__div">
      <div class="tmobile-msws__div__calendar">
        <div class="tmobile-msws__div__calendar__div">
          <table class="tmobile-msws__div__calendar__div__table" ref="calendarTable">
            <thead>
              <tr class="tmobile-msws__div__calendar__div__table__head">
                <th>Employees</th>
                <th>SUN 01</th>
                <th>MON 02</th>
                <th>TUE 03</th>
                <th id="activeColumn" class="active-column" :style="cssVars">WED 04</th>
                <th>THU 05</th>
                <th>FRI 06</th>
                <th>SAT 07</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td colspan="8" class="tmobile-msws__div__calendar__div__table__e-group">
                  ASSISTENT MANAGER
                </td>
              </tr>

              <tr class="tmobile-msws__div__calendar__div__table__e-row">
                <td>Kai Thompson</td>
                <td class="full-availability"></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td><span class="shift-another-location">OTHER LOC</span></td>
                <td></td>
              </tr>
              <tr class="tmobile-msws__div__calendar__div__table__e-row">
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
                  <div class="partial-availability-inner">
                    <span class="long-timing-tag">08AM - 03PM</span>
                  </div>
                </td>
                <td></td>
                <td></td>
              </tr>

              <tr>
                <td class="tmobile-msws__div__calendar__div__table__e-group" colspan="8">
                  SALES REPRESENTIVE
                </td>
              </tr>

              <tr class="tmobile-msws__div__calendar__div__table__e-row">
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
              <tr class="tmobile-msws__div__calendar__div__table__e-row">
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
              <tr class="tmobile-msws__div__calendar__div__table__e-row">
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
                <td class="tmobile-msws__div__calendar__div__table__e-group" colspan="8">
                  CUSTOMER CARE
                </td>
              </tr>
              <tr class="tmobile-msws__div__calendar__div__table__e-row">
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
              <tr class="tmobile-msws__div__calendar__div__table__e-row">
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
        <div class="tmobile-msws__hint-section">
          <div class="tmobile-msws__hint-section__div">
            <table class="tmobile-msws__hint-section__hint">
              <tr>
                <td><span class="short-timing-tag">XX XX - XX XX</span></td>
                <td>Short Shift</td>
                <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>

                <td><span class="exception-tag">*EXCP</span></td>
                <td>Exception</td>
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

                <td><span class="shift-another-location">Other LOC</span></td>
                <td>Shift Another Location</td>
                <td>&nbsp; &nbsp; &nbsp; &nbsp;</td>
                <td>
                  <div style="margin-top: -10px" class="partial-availability">
                    <div class="partial-availability-inner"></div>
                  </div>
                </td>
                <td>Partial Availability</td>
              </tr>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
* {
  font-family: 'Lato';
  margin: 0px;
  padding: 0px;
}

.tmobile-msws {
  table {
    table-layout: auto;
  }
  &__title {
    display: flex;
    padding: 20px;
    align-items: center;

    &__heading {
      width: 90%;
      font-size: 37px;
      color: #121212;
      font-weight: 800;

      h4 {
        font-size: 13px;
      }
    }

    &__back {
      flex: 1;
      text-align: right !important;
      margin-top: -38px;
    }
  }

  &__subheading {
    margin-top: 0px;
    display: flex;
    text-align: center;
    font-size: 18px;

    &__borderless {
      flex: 1;
      padding: 5px;
      border-bottom: 1px solid rgb(219, 200, 200);
      cursor: pointer;
    }

    &__border {
      width: 50%;
      border-bottom: 4px solid red;
      padding: 5px;
      cursor: pointer;
    }
  }

  &__calendar {
    display: flex;
    text-align: right;
    font-size: 20px;
    border-bottom: 1px solid rgb(219, 200, 200);
    padding: 15px;

    .icon-outer {
      display: flex;
      align-items: center;
      float: right;
      font-weight: 700;
    }

    &__detail {
      width: 60%;
      font-weight: 700;

      .icon {
        cursor: pointer;
        background-color: #f2f1f3;
        border-radius: 50%;
        padding: 7px 9px;
        height: 12px;
      }
    }

    &__event {
      flex: 1;
      font-weight: 700;

      .icon {
        cursor: pointer;
        background-color: #f2f1f3;
        border-radius: 50%;
        padding: 7px;
        height: 12px;
      }
    }
  }

  &__div {
    display: flex;

    &__calendar {
      width: 100%;
      border: 1px solid rgb(219, 200, 200);
      background-color: #f4f4f4;
      padding: 20px;

      &__div {
        overflow-y: auto;
        overflow-x: scroll;
        height: 80%;
        width: 100%;

        &__table {
          border-collapse: collapse;
          width: 100%;

          &__e-group {
            background-color: rgb(230, 227, 227);
            padding-top: 8px !important;
            padding-bottom: 8px !important;
            text-align: left !important;
          }
          &__e-row {
            background-color: #ffffff;

            td {
              &:first-child {
                font-size: 16px !important;
                font-weight: normal;
                text-align: left !important;
                width: 320px;
              }
            }
            td {
              padding-top: 25px;
              padding-bottom: 25px;
            }
          }

          &__head {
            background: #ffffff;
            position: sticky;
            top: 0;
            font-size: 12px;

            th {
              &:first-child {
                font-size: 16px !important;
                font-weight: normal;
                text-align: left !important;
                width: 320px;
              }
            }
          }

          th {
            padding: 7px 5px 7px 5px;
            border: 1px solid #626d5c;
            width: 100px;
            text-align: center;
            width: 120px;
            padding-top: 10px !important;
            padding-bottom: 10px !important;
          }

          td {
            padding: 7px 5px 7px 5px;
            border: 1px solid #626d5c;

            width: 100px;
            text-align: center;
          }
        }
      }
    }
  }

  .anchor {
    text-decoration: none;
    color: #0f0c0c;
  }

  &__hint-section {
    display: flex;

    &__div {
      width: 100%;
      border: 1px solid rgb(219, 200, 200);
      background-color: #fffcfc;
      padding: 0px;
      border-radius: 5px;
      margin-top: 20px;
      font-size: 12px;
    }

    &__hint {
      padding: 5px 10px;
      td {
        padding: 8px;
      }

      .hint_long-timing {
        display: block;
        padding-left: 30px;
        padding-right: 30px;
        padding-top: 3px;
        padding-bottom: 3px;
        font-size: 12px;
        line-height: 20px;
        margin-bottom: 2px;
        border-radius: 25px;
        background-color: #d1d1d1;
        border: 1px solid #626d5c;
      }
    }
  }

  .full-availability {
    position: relative;

    &:after {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      width: 0;
      height: 0;
      display: block;
      border-left: 20px solid transparent;
      border-bottom: 20px solid transparent;
      border-top: 20px solid #807878;
    }
  }

  .partial-availability {
    height: 100% !important;
    position: relative;

    &:after {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      display: inline-block;
      margin-right: 1px;
      margin-top: 1px;
      width: 20px;
      height: 20px;
      border-top: 2px solid #807878;
      border-right: 2px solid #807878;
    }
  }

  .partial-availability-inner {
    &:after {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      display: block;
      margin-right: 4px;
      margin-top: 4px;
      width: 13px;
      height: 13px;
      border-top: 2px solid #807878;
      border-right: 2px solid #807878;
    }
  }

  .not-scheduled {
    height: 100% !important;
    background: #ffffff;
    position: relative;

    &::after {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      border: 2px dashed #807878;
    }
  }

  .not-scheduled-inner {
    &::after {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      width: 0;
      display: block;
      margin-top: 3px;
      margin-right: 3px;
      border-left: 20px solid transparent;
      border-bottom: 20px solid transparent;
      border-top: 20px solid #807878;
    }
  }

  .short-timing-tag {
    display: inline-block;
    padding-left: 11px;
    padding-right: 11px;
    padding-top: 3px;
    padding-bottom: 3px;
    font-size: 12px;
    line-height: 20px;
    border-radius: 25px;
    background-color: #d1d1d1;
    margin-bottom: 2px;
    border: 1px solid #626d5c;
  }

  .long-timing-tag {
    display: block;
    padding-left: 15px;
    padding-right: 15px;
    padding-top: 3px;
    padding-bottom: 3px;
    font-size: 12px;
    line-height: 20px;
    margin-bottom: 2px;
    border-radius: 25px;
    background-color: #d1d1d1;
    border: 1px solid #626d5c;
  }

  .exception-tag {
    display: inline;
    padding-left: 40px;
    padding-right: 45px;
    padding-top: 3px;
    padding-bottom: 3px;
    font-size: 12px;
    border-radius: 3px;
    background-color: #d1d1d1;
    border: 1px solid #626d5c;
  }

  .shift-another-location {
    display: block;
    padding-left: 15px;
    padding-right: 15px;
    padding-top: 3px;
    padding-bottom: 3px;
    font-size: 12px;
    border-radius: 25px;
    border: 1px dashed #626d5c;
    margin-bottom: 2px;
    line-height: 24px;
  }

  .active-column {
    height: 100% !important;
    position: relative;

    &::after {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      left: 0;
      display: inline-block;
      width: 100%;
      height: 0px;
      height: var(--height);
      border: 2px solid #807878;
    }
  }
}
</style>
