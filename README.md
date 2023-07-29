# Java-script
Java script code
*******************Code for input only numeric value and . (period)******************************
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
