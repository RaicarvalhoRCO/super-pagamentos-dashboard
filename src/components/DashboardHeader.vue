<template>
    <div class="d-flex align-items-center gap-3 p-3 rounded">
        <div class="d-flex w-100 gap-3">
            <button class=" new_bill_button btn btn-primary d-flex align-items-center">
                <span>Nova cobrança</span>
                <IconPlus />
            </button>

            <div class="vr"></div>

            <div class="input-group rounded-pill bg-white px-3 selector">
                <IconCalendar />
                <select class="form-select border-0 shadow-none">
                    <option>Período: Específico</option>
                    <option>Mês atual</option>
                    <option>Últimos 30 dias</option>
                </select>
            </div>


            <div class="input-group rounded-pill border bg-white px-3 selector_date">
                <IconCalendar class="icon-calendar" />
                <input type="date" class="form-control border-0 shadow-none custom-date-input_from"
                    value="2020-06-10" />
                <span>|</span>
                <input type="date" class="form-control border-0 shadow-none custom-date-input_to" value="2025-01-30" />
            </div>
        </div>
        <div class="bill_type d-flex gap-3">
            <div class="input-group rounded-pill border bg-white px-3 selector_bill">
                <select class="form-select border-0 shadow-none">
                    <option>Tipo de cobrança</option>
                    <option>PIX</option>
                    <option>Boleto</option>
                    <option>Cartão</option>
                </select>
            </div>

            <button class="btn btn-light bg-white rounded-circle border download-btn">
                <i class="bi bi-download"></i>
            </button>
        </div>
    </div>
</template>
<script>

import IconPlus from './icons/IconPlus.vue';
import IconCalendar from './icons/IconCalendar.vue';

export default {
    name: "DashboardHeader",
    components: {
        IconPlus,
        IconCalendar
    }
};
</script>

<style scoped>
.dashboard-header {
    background-color: #f8f9fa;
    border-bottom: 1px solid #ddd;
    padding: 16px;
}

.filters {
    display: flex;
    align-items: center;
    justify-content: flex-end;
}

.filter-item {
    margin-right: 16px;
}

.new_bill_button {
    width: 180px;
    height: 46px;
    border-radius: 32px;
}

.new_bill_button span {
    font-family: Plus Jakarta Sans;
    font-weight: 600;
    font-size: 14px;
    line-height: 100%;
    width: 103px;
    margin-right: 10px;
}

.selector {
    width: 200px;
    padding: 0px 6px 0px 10px !important;
}

.selector_bill {
    width: 200px;
}

.selector,
.selector_date,
.selector_bill {
    height: 48px;
    align-items: center;
    border: 1px solid #D9D9D9;
}

.selector select,
.selector_date select,
.selector_bill select {
    font-family: Plus Jakarta Sans;
    font-weight: 600;
    font-size: 14px;
    padding: 5px;
}

.selector_date {
    position: relative;
    width: 360px;
    font-family: Plus Jakarta Sans;
    font-weight: 600;
    font-size: 14px;
    padding: 5px;
}

.selector_date .icon-calendar {
    position: absolute;
    left: 12px;
    top: 50%;
    transform: translateY(-50%);
    pointer-events: none;
    z-index: 10;
}

.custom-date-input_from {
    padding-left: 20px;

}

.custom-date-input_to {
    padding-left: 20px;
}

.custom-date-input_from::-webkit-calendar-picker-indicator,
.custom-date-input_to::-webkit-calendar-picker-indicator {
    background-image: url('data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-down" viewBox="0 0 24 24"%3E%3Cpath fill-rule="evenodd" d="M1.646 4.646a.5.5 0 0 1 .708 0L8 10.293l5.646-5.647a.5.5 0 0 1 .708.708l-6 6a.5.5 0 0 1-.708 0l-6-6a.5.5 0 0 1 0-.708z"/%3E%3C/svg%3E');
    background-repeat: no-repeat;
    background-position: center;
    background-size: 16px;
    opacity: 1;
    pointer-events: auto;
}

.download-btn {
    width: 48px;
    border: 1px solid #D9D9D9;
}
</style>
