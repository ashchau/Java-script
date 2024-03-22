****************Center align text from both side properly**********
<style>
        .listtype {
            text-align: justify;
        }

        h4,p {
            text-align: justify;
        }
</style>

# Java-script
Java script code
//*******************Code for input only numeric value and . (period)******************************
<script>
        var validNumber = new RegExp(/^\d*\.?\d*$/);
        var lastValid = "";
        function validateNumber(elem) {
            if (validNumber.test(elem.value)) {
                lastValid = elem.value;
            }
            else {
                elem.value = lastValid;
            }
        }
    </script>
    <asp:TextBox ID="txtpf" runat="server" CssClass="form-control" oninput="validateNumber(this);"></asp:TextBox>
    
    //****************Code for datepicker, Validate date and split input as date formate and input only numeric values************
    
    <script language="javascript" type="text/javascript">
        function addDashes2(aa) {
            //alert("validateNumKey1");

            if (document.getElementById(aa).value != null) {
                var currValue = document.getElementById(aa).value;
                var a = currValue.split("/").join("");

                if (a.length > 3)
                    document.getElementById(aa).value = a.substr(0, 2) + "/" + a.substr(2, 2) + "/" + a.substr(4);
                else
                    if (a.length > 1)
                        document.getElementById(aa).value = a.substr(0, 2) + "/" + a.substr(2)
            }
            else {
                alert("else");
            }

        }
        function validateNumKey() {
            var inputKey = event.keyCode;
            // alert("validateNumKey");
            var returnCode = true;

            if (inputKey > 47 && inputKey < 58) // numbers
            {
                return;
            }
            else {
                returnCode = false;
                event.keyCode = 0;
            }
            //event.returnValue = returnCode;
            return returnCode;
        }
        function validateDate(fld) {
            if (document.getElementById(fld).value == '') {
            }
            else {
                var RegExPattern = /^(?:(?:(?:0?[1-9]|1\d|2[0-8])\/(?:0?[1-9]|1[0-2]))\/(?:(?:1[6-9]|[2-9]\d)\d{2}))$|^(?:(?:(?:31\/0?[13578]|1[02])|(?:(?:29|30)\/(?:0?[1,3-9]|1[0-2])))\/(?:(?:1[6-9]|[2-9]\d)\d{2}))$|^(?:29\/0?2\/(?:(?:(?:1[6-9]|[2-9]\d)(?:0[48]|[2468][048]|[13579][26]))))$/;
                var errorMessage = 'Please enter valid date';
                if ((document.getElementById(fld).value.match(RegExPattern)) && (document.getElementById(fld).value != '')) {
                    // alert('Date is OK');        
                }
                else {

                    alert(errorMessage);
                    //fld.focus(); 
                    document.getElementsById("ctl00_ContentPlaceHolder1_lbldateerror").style.visiblity = true;
                    document.getElementById(fld).value = '';
                }
            }
        }
         $(function dtTimePicker() {
                $(".tenderdate").datepicker({
                    dateFormat: 'dd-mm-yy',
                    changeMonth: true,
                    changeYear: true
    
                });
            });
    </script>
     <asp:TextBox ID="Txt_TenderPubDt" runat="server" Enabled="False" MaxLength="10" onkeyup="addDashes2('ctl00_ContentPlaceHolder1_Txt_TenderPubDt')" onfocusout="validateDate('ctl00_ContentPlaceHolder1_Txt_TenderPubDt')" onkeypress="validateNumKey()" placeholder="DD-MM-YYYY" CssClass="tenderdate"></asp:TextBox>
