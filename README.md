function autoTab(e) {
            var TAB = 9, SHIFT = 16;
            var evt = (e != null) ? e : event;
            var el = (evt.target) ? evt.target : evt.srcElement
            var key = (evt.keyCode) ? evt.keyCode : evt.which;

            if (key == TAB || key == SHIFT) return; //tabbing shouldn't change the focus

            if (el.value.length == el.maxLength) {
                var col = document.forms[0].elements;
                var len = col.length;

                for (i = 0; i < len; i++) {
                    if (col[i] == el && i != len - 2) {
                        col[i + 1].focus();
                        col[i + 1].select();
                        return;
                    }
                }
            }
        }
