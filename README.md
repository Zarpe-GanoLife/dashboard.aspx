<%@ Page Title="Dashboard" Language="C#" MasterPageFile="~/Site.master" AutoEventWireup="true" CodeFile="Dashboard.aspx.cs" Inherits="Dashboard" culture="auto" meta:resourcekey="PageResource1" uiculture="auto" %>

<asp:Content ID="HeaderContent" runat="server" ContentPlaceHolderID="HeadContent">
</asp:Content>

<asp:Content ID="BodyContent" runat="server" ContentPlaceHolderID="MainContent">

    <script type="text/javascript" src='<%= System.Configuration.ConfigurationManager.AppSettings["WebPagePath"]%>/Scripts/Dashboard.js<%= System.Configuration.ConfigurationManager.AppSettings["WebVersion"] %>'></script>



<!-- CONTENIDO -->
<div class="content-wrapper">

<div id="contenedor_de_pagina" class="ancho_de_pagina">
    

<!-- Contenido -->
<div id="contenido_de_pagina" >
       
<asp:UpdatePanel ID="UpdatePanelDashboardTitle" runat="server">
<ContentTemplate>

       <div class="fila-ajustable" >

              <div class="columna_ancho12" > 
              <h2><asp:Label ID="lblPageTitle" runat="server" Text="Bienvenido al Sistema de Gestión Empresarial: Ganolife 365" meta:resourcekey="lblPageTitleResource1" >
              </asp:Label><asp:Label ID="Label21" runat="server" Text="" Width="150px"></asp:Label>
               <asp:Button ID="btnReportsManagement" runat="server" 
                      Text="Ver Dashboard Gerencial" TabIndex="17" 
                        CssClass="boton_basico boton_blanco" 
                      onclick="btnReportsManagement_Click" />
              </h2>
               
              <hr>
              </div>

        </div>

</ContentTemplate>
</asp:UpdatePanel>


        <!-- Bloque -->
        <div class="fila-ajustable" >


<asp:UpdatePanel ID="UpdatePanel1" runat="server">
<ContentTemplate>


            <!-- foto -->
            <div class="columna_ancho3">
                <div class="bloque_basico color_de_bloque" style="">

                <div class="titulo_de_bloque2"><h4></h4></div>


                <div style="border:1px solid #e0e0e0 !important; border-bottom-left-radius: 7px; border-bottom-right-radius: 7px; min-height: 400px; ">
                <div style="text-align: center; background-color: #969696; ">
                <br> 

                <!-- Div foto y nombre -->
                <div class="centrar" id="divProfileInfo" runat="server" clientidmode="Static">
                    <table width="100%" border="0" align="center" cellpadding="0" cellspacing="0"  >
                        <tr>
                        <td align="center" valign="top">
                        <asp:Image ID="imgUserPhoto1" runat="server" ClientIDMode="Static" ImageUrl="~/Styles/2015/img/user-photo.jpg" class="imagen_circular" 
                        Width="110px" Height="110px"  style="border: 1px Solid #c4c4c4; " meta:resourcekey="imgUserPhoto1Resource1"/>
                        </td>
                        </tr>
                    </table>

                <h4><asp:Label ID="lbName" runat="server" ForeColor="White" Font-Bold="True" meta:resourcekey="lbNameResource1" ></asp:Label></h4>
                <asp:Label ID="lbInfo" runat="server" Text="Area de Sistemas" ForeColor="White" meta:resourcekey="lbInfoResource1" ></asp:Label>

                <br><br>
                <div data-tooltip="Cambiar foto" class="tooltip-bottom" runat="server" clientidmode="Static" meta:resourcekey="dtChangePhotoResource1">
                    <asp:ImageButton ID="btnUserPhotoEdit" runat="server" TabIndex="11"
                    CssClass="efecto_zoom icono_adaptable_add" ImageUrl="~/Styles/2015/img/boton_editar.png" 
                    OnClick="btnUserPhotoEdit_Click"  meta:resourcekey="btnUserPhotoEditResource1" />
                </div>

                </div>

                <br>

                <!-- Div para subir foto -->
                <div id="divUploadPhoto" runat="server" clientidmode="Static" visible="False">

                        <br>
                        <table width="90%" border="0" align="center" cellpadding="0" cellspacing="0">
                          <tr>
                            <td align="center">

                            <div id="div-input-falso"><input name="file-falso" type="text" id="file-falso" class="campo_texto_carpeta_dahsboard" 
                            readonly="readonly" placeholder="Examinar" />
                            <asp:RequiredFieldValidator ID="rfvUpPhoto" runat="server" ErrorMessage="*" ControlToValidate="upPhoto" 
                            Font-Bold="True" ForeColor="Red" ValidationGroup="UploadPhoto" meta:resourcekey="rfvUpPhotoResource1" ></asp:RequiredFieldValidator>
                            </div>

                            <asp:FileUpload ID="upPhoto" runat="server" Font-Bold="False" CssClass="file_oculto" meta:resourcekey="upPhotoResource1" 
                            onchange="document.getElementById('file-falso').value = this.value;"/>
                            </td>
                          </tr>
                          <tr>
                            <td align="center">
                            <br>

                            <table width="20%" border="0" align="center" cellpadding="2" cellspacing="0" style="margin-left:20px">
                                <tr>

                                <td align="left">
                                <div data-tooltip="Actualizar foto" class="tooltip-bottom" style="width:50px; ">
                                <asp:ImageButton ID="btnUpdatePhoto" runat="server" 
                                        CssClass="efecto_zoom icono_adaptable_salir" style="margin-top:0px !important;" ImageUrl="~/Styles/2015/img/icono_nota_guardar_xl_on.png" 
                                ValidationGroup="UploadPhoto" OnClick="btnUpdatePhoto_Click" />
                                </div>
                                </td>

                                <td align="left">
                                <div data-tooltip="Eliminar foto" class="tooltip-bottom" style="width:50px; ">
                                <asp:ImageButton ID="btnRemovePhoto" runat="server" 
                                        CssClass="efecto_zoom icono_adaptable_salir" style="margin-top:0px !important;" ImageUrl="~/Styles/2015/img/icono_nota_borrar_xl_on.png" 
                                OnClick="btnRemovePhoto_Click" meta:resourcekey="btnRemovePhotoResource1" />
                                </div>
                                </td>

                                <td align="left">
                                <div data-tooltip="Salir" class="tooltip-bottom" style="width:50px; ">
                                <asp:ImageButton ID="btnClosePhoto" runat="server" 
                                        CssClass="efecto_zoom icono_adaptable_salir" style="margin-top:0px !important;" ImageUrl="~/Styles/2015/img/icono_nota_cerrar_xl_on.png" 
                                OnClick="btnClosePhoto_Click" meta:resourcekey="btnClosePhotoResource1" />
                                </div>
                                </td>

                                </tr>
                            </table>

                            </td>
                          </tr>
                        </table>

                        <br>
                        <asp:Label ID="lbMessagePhoto" runat="server" 
                        CssClass="etiqueta etiqueta_azul" meta:resourcekey="lbMessagePhotoResource1" ></asp:Label>
                        <br>

                </div>

                </div>


                <!-- Correo y fono -->
                <table width="100%" border="0" align="center" cellpadding="0" cellspacing="0">
                  <tr>
                    <td width="11%" >
                    </td>
                    <td width="89" >
                    <br>
                    <asp:Image ID="imgIconMail" runat="server" ImageUrl="~/Styles/2015/img/icono_email.png" style="margin-right:12px;" meta:resourcekey="imgIconMailResource1" />
                    <asp:Label ID="lbEmail" runat="server" meta:resourcekey="lbEmailResource1" ></asp:Label>
                    <br><br>
                    <asp:Image ID="imgIconMovil" runat="server" ImageUrl="~/Styles/2015/img/icono_movil.png" style="margin-right:12px;" meta:resourcekey="imgIconMovilResource1" />
                    <asp:Label ID="lbPhone" runat="server" Text="999999999" meta:resourcekey="lbPhoneResource1" ></asp:Label>
                    <br>
                    </td>
                  </tr>
                </table>




                </div>
                </div>
            </div>



</ContentTemplate>
<Triggers>
    <asp:PostBackTrigger ControlID="btnUpdatePhoto" />
</Triggers>
</asp:UpdatePanel>


            <!-- Correo -->
<%--            <div class="columna_ancho6" >
            <div class="tabs_de_bloque color_de_bloque bloque_basico " style="min-height: 369px; " >
                    <ul class="menu menu_con_tabs" data-toggle="tabs">
                        <li class="active">
                        <a href="#contenido_tab1"><asp:Label ID="lblTabText1" runat="server" Text="Bandeja de Entrada"></asp:Label></a>
                        </li>
                        <li>
                        <a href="#contenido_tab2"><asp:Label ID="lblTabText2" runat="server" Text="Nuevo mensaje"></asp:Label></a>
                        </li>
                        <li>
                        <a href="#contenido_tab3"><asp:Label ID="lblTabText3" runat="server" Text="Borradores"></asp:Label></a>
                        </li>
                        <li>
                        <a href="#contenido_tab4"><asp:Label ID="lblTabText4" runat="server" Text="Configuración"></asp:Label></a>
                        </li>
                    </ul>
                            
                    <div class="tabs_contenido" style="min-height: 276px; ">
                        <!-- Tab 1 -->
                        <div class="tab_panel active" id="contenido_tab1" >

                            <div class="texto_centrado" >
                                      
                                <br>
                                

                            </div>

                        </div>

                        <!-- Tab 2 -->
                        <div class="tab_panel" id="contenido_tab2">
                            <div class="texto_centrado">
                                <br>
                                <asp:Label ID="lblText2" runat="server" Text="Contenido 2"></asp:Label>
                            </div>
                        </div>

                        <!-- Tab 3 -->
                        <div class="tab_panel" id="contenido_tab3">
                            <div class="texto_centrado">
                                <br>
                                <asp:Label ID="lblText3" runat="server" Text="Contenido 3"></asp:Label>
                            </div>
                        </div>

                        <!-- Tab 4 -->
                        <div class="tab_panel" id="contenido_tab4" >
                            <div class="texto_centrado"> 
                                <br>
                                <asp:Label ID="lblText4" runat="server" Text="Contenido 4"></asp:Label>
                            </div>
                        </div>


                        </div>

            </div>
            </div>--%>

            <!-- Ventas Mensuales Region 3 -->
           <div class="columna_ancho9" id = "Sales" runat="server" >
                <div class="bloque_basico color_de_bloque" style="background-color: #969696;">

                <div class="titulo_de_bloque" style="background-color: #969696 !important;">
                    <h4><asp:Label ID="Label1" runat="server" Text="Ventas Mensuales - Comparativo al dia actual" 
                             ></asp:Label></h4>

                           
                </div>

                <div style="min-height: 234px; ">
                <iframe src="Modules/Reports/Dashboard/Column.aspx" width="100%" height="364" frameBorder="0" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen id="iframeEmail" runat="server"></iframe>
                </div>



                </div>
            </div>


           <!-- Ventas Mensuales Peru -->
           <div class="columna_ancho9" id = "SalesPeru" runat="server" >
                <div class="bloque_basico color_de_bloque" style="background-color: #969696;">

                <div class="titulo_de_bloque" style="background-color: #969696 !important;">
                    <h4><asp:Label ID="Label3" runat="server" Text="Ventas Mensuales - Comparativo al dia actual" ></asp:Label></h4>
                    <asp:Label ID="Label22" runat="server" Text="" Width="150px"></asp:Label>
                    <asp:DropDownList ID="ddlReportYear" runat="server" AutoPostBack="True" 
                        onselectedindexchanged="ddlReportYear_SelectedIndexChanged">
                        <asp:ListItem Selected="True">2018</asp:ListItem>
                        <asp:ListItem>2017</asp:ListItem>
                        <asp:ListItem>2016</asp:ListItem>
                        <asp:ListItem>2015</asp:ListItem>
                        <asp:ListItem>2014</asp:ListItem>
                        <asp:ListItem>2013</asp:ListItem>
                    </asp:DropDownList>
                     <br />
                     <br />
                    <asp:HiddenField ID="hdReportYear" runat="server" />
                    <asp:HiddenField ID="hdparamReportYear" runat="server" />
                </div>
               
                <div style="min-height: 234px; ">
                <iframe id="iframe1" src="Modules/Reports/Dashboard/PE/Sales.aspx" runat="server"  width="100%" height="364" frameBorder="0" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen ></iframe>
                                
                </div>

                </div>
            </div>


           <!-- Ventas Mensuales El Salvador -->
           <div class="columna_ancho9" id = "SalesSV" runat="server" >
                <div class="bloque_basico color_de_bloque" style="background-color: #969696;">

                <div class="titulo_de_bloque" style="background-color: #969696 !important;">
                    <h4><asp:Label ID="Label7" runat="server" Text="Ventas Mensuales - Comparativo al dia actual "></asp:Label></h4>
                     <asp:Label ID="Label23" runat="server" Text="" Width="150px"></asp:Label>
                    <asp:DropDownList ID="ddlReportYearSV" runat="server" AutoPostBack="True" 
                        onselectedindexchanged="ddlReportYearSV_SelectedIndexChanged">
                        <asp:ListItem Selected="True">2018</asp:ListItem>
                        <asp:ListItem>2017</asp:ListItem>
                        <asp:ListItem>2016</asp:ListItem>
                        <asp:ListItem>2015</asp:ListItem>
                        <asp:ListItem>2014</asp:ListItem>
                        <asp:ListItem>2013</asp:ListItem>
                    </asp:DropDownList>
                     <br />
                     <br />
                </div>

                <div style="min-height: 234px; ">
                <iframe src="Modules/Reports/Dashboard/SV/Sales.aspx" width="100%" height="364" frameBorder="0" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen id="iframe2" runat="server"></iframe>
                </div>

                </div>
            </div>
            <!-- Ventas Mensuales Warehouse Miraflores (Peru) -->
             <div class="columna_ancho9" id = "SalesPEMiraflores" runat="server" >
                <div class="bloque_basico color_de_bloque" style="background-color: #969696;">

                <div class="titulo_de_bloque" style="background-color: #969696 !important;">
                    <h4><asp:Label ID="Label18" runat="server" Text="Ventas Mensuales"></asp:Label></h4>
                </div>

                <div style="min-height: 234px; ">
                <iframe src="Modules/Reports/Dashboard/PE/SalesbyWarehouse1.aspx" width="100%" height="364" frameBorder="0" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen id="iframe3" runat="server"></iframe>
                </div>

                </div>
            </div>

            <!-- Ventas Mensuales Los Olivos (Peru)-->
             <div class="columna_ancho9" id = "SalesPEOlivos" runat="server" >
                <div class="bloque_basico color_de_bloque" style="background-color: #969696;">

                <div class="titulo_de_bloque" style="background-color: #969696 !important;">
                    <h4><asp:Label ID="Label19" runat="server" Text="Ventas Mensuales"></asp:Label></h4>
                </div>

                <div style="min-height: 234px; ">
                <iframe src="Modules/Reports/Dashboard/PE/SalesbyWarehouse3.aspx" width="100%" height="364" frameBorder="0" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen id="iframe4" runat="server"></iframe>
                </div>

                </div>
            </div>


            <!-- Ventas Mensuales Heroes (El Salvador) -->
             <div class="columna_ancho9" id = "SalesSVHeroes" runat="server" >
                <div class="bloque_basico color_de_bloque" style="background-color: #969696;">

                <div class="titulo_de_bloque" style="background-color: #969696 !important;">
                    <h4><asp:Label ID="Label20" runat="server" Text="Ventas Mensuales"></asp:Label></h4>
                </div>

                <div style="min-height: 234px; ">
                <iframe src="Modules/Reports/Dashboard/PE/SalesbyWarehouse1.aspx" width="100%" height="364" frameBorder="0" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen id="iframe5" runat="server"></iframe>
                </div>

                </div>
            </div> 


        </div>



        <!-- Bloque -->
        <div class="fila-ajustable " >

        <!-- Meta semanal -->
        <%--<div class="columna_ancho3" >
                <div class="bloque_basico color_de_bloque" style="background-color: #27c266;">
                <div class="titulo_de_bloque">
                    <h4><asp:Label ID="lblBlockTitle4" runat="server" Text="Meta Semanal" meta:resourcekey="lblCDAResource1"></asp:Label></h4>
                </div>
                <div style="min-height: 193px; ">   
                <div class="fila-ajustable columnas">

                <table width="100%" border="0" align="center" cellpadding="20" cellspacing="0">
                  <tr>
                    <td width="33%" valign="top">                  
                    </td>
                    <td width="33%" valign="top">
                    </td>
                    <td width="34%" valign="top">
                    </td>
                  </tr>
                </table>
                </div
                </div>
                </div>
            </div>--%>



<asp:UpdatePanel ID="upNotes" runat="server">
<ContentTemplate>


        <!-- Notas -->
            <div class="columna_ancho3">
                <div class="bloque_basico color_de_bloque" >

                <div class="titulo_de_bloque2">
                    <h4></h4>
                </div>

                <div class="contenido_de_bloque" style="min-height: 360px; ">
            <div  id="divNotes_Tab_2" runat="server" clientidmode="Static">

                        <!-- Lista de notas -->
                        <div id="divCRM_Notes_List" runat="server" clientidmode="Static" >

                             <h4><asp:Label ID="lblTabNotes_Title1" runat="server" Text="Notas Personales" 
                                     Font-Bold="True" meta:resourcekey="lblTabNotes_Title1Resource1" ></asp:Label></h4>

                             <div data-tooltip="Añadir nota" class="colocar_derecha tooltip-bottom" style="margin-top: -40px; " runat="server" clientidmode="Static"  meta:resourcekey="dtAddNoteResource1">
                                <asp:ImageButton ID="btnCRMNotesAdd" runat="server" CssClass="efecto_zoom icono_adaptable_add" TabIndex="12"
                                    ImageUrl="~/Styles/2015/img/boton_mas.png" onclick="btnCRMNotesAdd_Click" 
                                     meta:resourcekey="btnCRMNotesAddResource1" />
                            </div>
                             <hr>

                             <div class="controles-grupales" style="text-align: center " runat="server">
                             <asp:TextBox ID="txtCRMNotesFilter" runat="server" ClientIDMode="Static" 
                                     CssClass="campo_texto_busqueda" TabIndex="13" 
                             data-toggle="tooltip" data-placement="right" title="Buscar Notas" 
                                     placeholder="Buscar Nota" meta:resourcekey="txtCRMNotesFilterResource1"></asp:TextBox>   
                             </div>
                             <br>

                              <div style="height:183px; overflow-y: scroll; overflow-x: hidden;">
                            
                            <asp:GridView ID="gvCRMNotes" runat="server" ClientIDMode="Static" class="tabla6" 
                                      style="" BackColor="White" CellPadding="0" AutoGenerateColumns="False"
                             OnRowDataBound="gvNotes_OnRowDataBound" meta:resourcekey="gvCRMNotesResource1">
                            <Columns>
                            <asp:BoundField DataField="DefaultFlag" meta:resourcekey="BoundFieldResource1" >
                            <ItemStyle CssClass="etiqueta_status" HorizontalAlign="Center"  Width="20%" />
                            </asp:BoundField>
                            <asp:BoundField DataField="Subject" meta:resourcekey="BoundFieldResource2">
                            <ItemStyle HorizontalAlign="Left"  Width="50%" />
                            </asp:BoundField>
                            <asp:BoundField DataField="CreatedDate" DataFormatString="{0:dd/MM}" 
                                    meta:resourcekey="BoundFieldResource3">
                            <ItemStyle CssClass="texto_en_tablet2" ForeColor="#27C266" 
                                    HorizontalAlign="Center"  Width="15%" />
                            </asp:BoundField>

                            <asp:TemplateField meta:resourcekey="TemplateFieldResource1" >
                                <ItemTemplate>

                                        <asp:HiddenField ID="hdID" runat="server" Value='<%# DataBinder.Eval(Container.DataItem, "ID") %>' Visible="False" />
                                        <asp:HiddenField ID="hdSubject" runat="server" Value='<%# DataBinder.Eval(Container.DataItem, "Subject") %>' Visible="False" />
                                        <asp:HiddenField ID="hdDefaultFlag" runat="server" Value='<%# DataBinder.Eval(Container.DataItem, "DefaultFlag") %>' Visible="False" />
                                        <asp:HiddenField ID="hdColorNote" runat="server" Value='<%# DataBinder.Eval(Container.DataItem, "ColorNote") %>' Visible="False" />
                                        <asp:ImageButton ID="btnCRMNotesEdit" runat="server" TabIndex="14" 
                                            ImageUrl="~/Styles/2015/img/icono_flecha_de.png" 
                                            onclick="btnCRMNotesEdit_Click" meta:resourcekey="btnCRMNotesEditResource1" />

                                </ItemTemplate>
                                <ItemStyle CssClass="datagrid" HorizontalAlign="Left" Width="15%"/>
                            </asp:TemplateField>

                            </Columns>
                            <FooterStyle BackColor="#F7DFB5" ForeColor="#8C4510" />
                            <HeaderStyle CssClass="gridview-header" />
                            <PagerStyle CssClass="gridview-pager" HorizontalAlign="Center" />
                            <SortedAscendingCellStyle BackColor="#FFF1D4" />
                            <SortedAscendingHeaderStyle BackColor="#B95C30" />
                            <SortedDescendingCellStyle BackColor="#F1E5CE" />
                            <SortedDescendingHeaderStyle BackColor="#93451F" />
                            </asp:GridView>
                            </div>

                        </div>


                        <!-- Nuevas Notas -->
                        <div id="divCRM_Notes_New" runat="server" visible="False"  >
                                
                                <asp:HiddenField ID="hdCRMNotesID" runat="server" Visible="False" />
                                <h4><asp:Label ID="lblTabNotes_title2" runat="server" Text="Nueva Nota" 
                                        Font-Bold="True" meta:resourcekey="lblTabNotes_title2Resource1" ></asp:Label></h4>
                                <asp:Label ID="lbTabNotes_Date" runat="server" Text="Fecha: " 
                                    meta:resourcekey="lbTabNotes_DateResource1" ></asp:Label> 
                                <asp:Label ID="lbCRMNotes_Date" runat="server" Text="30-10-2015" 
                                    ForeColor="#27C266" meta:resourcekey="lbCRMNotes_DateResource1" ></asp:Label>
                                <div data-tooltip="Salir" class="colocar_derecha tooltip-bottom" >
                                    <asp:ImageButton ID="btnCRMNotesClose" runat="server" 
                                        CssClass="efecto_zoom icono_adaptable_salir" 
                                        ImageUrl="~/Styles/2015/img/boton_cerrar.png" onclick="btnCRMNotesClose_Click" 
                                        meta:resourcekey="btnCRMNotesCloseResource1" />
                                </div>
                                <hr>
                   
                                <table width="100%" border="0" align="center" cellpadding="2" cellspacing="0" >
                  
                                  <tr runat="server" Visible="False">
                                    <td align="right" runat="server">
                                    <asp:Label ID="lblTabNotes_Category" runat="server" Text="Categoría" ></asp:Label>
                                    </td>
                                    <td runat="server">
                                    <asp:DropDownList ID="ddlCRMNotes_Category" runat="server" CssClass="campo_texto_select" >
                                    <asp:ListItem Text="Category 1" Value="1"></asp:ListItem>
                                    <asp:ListItem Text="Category 2" Value="2"></asp:ListItem>
                                    <asp:ListItem Text="Category 3" Value="3"></asp:ListItem>
                                    <asp:ListItem Text="Category 4" Value="4"></asp:ListItem>
                                    <asp:ListItem Text="Category 5" Value="5"></asp:ListItem>
                                    </asp:DropDownList>
                                    </td>
                                  </tr>

                                  <tr runat="server" Visible="False">
                                    <td align="right" runat="server">
                                    <asp:Label ID="lblTabNotes_Subcategory" runat="server" Text="Sub Categoría" ></asp:Label>
                                    </td>
                                    <td runat="server">
                                    <asp:DropDownList ID="ddlCRMNotes_Subcategory" runat="server" CssClass="campo_texto_select" >
                                    <asp:ListItem Text="SubCategory 1" Value="1"></asp:ListItem>
                                    <asp:ListItem Text="SubCategory 2" Value="2"></asp:ListItem>
                                    <asp:ListItem Text="SubCategory 3" Value="3"></asp:ListItem>
                                    <asp:ListItem Text="SubCategory 4" Value="4"></asp:ListItem>
                                    <asp:ListItem Text="SubCategory 5" Value="5"></asp:ListItem>
                                    </asp:DropDownList>
                                    </td>
                                  </tr>

                                  <tr runat="server" Visible="False">
                                    <td align="right" runat="server">
                                    <asp:Label ID="lblTabNotes_State" runat="server" Text="Estado" ></asp:Label>
                                    </td>
                                    <td runat="server">
                                    <asp:CheckBox id="toggle6" runat="server" ClientIDMode="Static" /><label for="toggle6"></label>
                                    </td>
                                  </tr>

                                  <tr>
                                    <td align="right" >
                                    <div style="margin-top:-10px; ">
                                    <asp:Label ID="lblTabNotes_Subject" runat="server" Text="Asunto" meta:resourcekey="lblTabNotes_SubjectResource1"></asp:Label>
                                    </div>
                                    </td>
                                    <td>
                                    <div data-tooltip="Asunto" class="tooltip-bottom" >
                                    <asp:TextBox ID="txtCRMNotes_Subject" runat="server" ClientIDMode="Static" 
                                         CssClass="campo_texto_simple_s"  MaxLength="30" meta:resourcekey="txtCRMNotes_SubjectResource1"></asp:TextBox>
                                    </div>
                                    <asp:RequiredFieldValidator ID="rfvCRMNotes_Subject" runat="server" 
                                            ControlToValidate="txtCRMNotes_Subject" ErrorMessage="*" Font-Bold="True" 
                                    ForeColor="Red" SetFocusOnError="True" ValidationGroup="ValidateCRMNotesSave" 
                                            meta:resourcekey="rfvCRMNotes_SubjectResource1"></asp:RequiredFieldValidator>
                                    </td>
                                  </tr>

                                  <tr>
                                    <td align="right" valign="top">
                                    <asp:Label ID="lblTabNotes_Answer" runat="server" Text="Descripción" meta:resourcekey="lblTabNotes_AnswerResource1" ></asp:Label>
                                    </td>
                                    <td>
                                    <div data-tooltip="Descripción" class="tooltip-bottom" >
                                    <asp:TextBox ID="txtCRMNotes_Description" runat="server" ClientIDMode="Static" 
                                            CssClass="campo_texto_notas_2"  MaxLength="30" TextMode="MultiLine" 
                                            meta:resourcekey="txtCRMNotes_DescriptionResource1"></asp:TextBox>
                                    </div>
                                    <asp:RequiredFieldValidator ID="rfvCRMNotes_Description" runat="server" ControlToValidate="txtCRMNotes_Description" ErrorMessage="*" Font-Bold="True" 
                                    ForeColor="Red" SetFocusOnError="True" ValidationGroup="ValidateCRMNotesSave" meta:resourcekey="rfvCRMNotes_DescriptionResource1"></asp:RequiredFieldValidator>
                                    </td>
                                  </tr>
                                  <tr>
                                    



                                <td align="right">
                                <asp:Label ID="lblTabNotes_Attend" runat="server" Text="Ingresado por" meta:resourcekey="lblTabNotes_AttendResource1" ></asp:Label>
                                </td>
                                <td>
                                    <asp:TextBox ID="txtCRMNotes_Enteredby" runat="server" ClientIDMode="Static" CssClass="campo_texto_simple_s"  MaxLength="30" Enabled="false"></asp:TextBox>           
                                </td>


                                <tr><td  colspan="2"><hr></td></tr>

                                    <!-- Contenido -->    
                                    <table width="100%" border="0" align="center" cellpadding="3" cellspacing="0" >
                                    <tr>
                                        <td align="left">
                                            <asp:Label ID="lblCurrentColorNote" runat="server" Text="Color Actual" ></asp:Label>
                                            <asp:Label ID="lblColorNote" runat="server" Text="" Visible = "false" ></asp:Label>
                                            <asp:Label ID="lblCRMNoteCellPhone" runat="server" Text="" Visible = "false" ></asp:Label>
                                            <asp:ImageButton ID="btn_CurrentColorNote" runat="server" CssClass="efecto_zoom icono_adaptable_add" 
                                                    ImageUrl="~/Styles/2015/img/boton_color0.png" CommandArgument="#FFFFFF" onclick="btn_ChangeColor_Click" />
                                        </td>
                                    </tr>
                                    </table>

                                <tr><td  colspan="2"><hr></td></tr>


                                    <table width="100%" border="0" align="center" cellpadding="3" cellspacing="0" >
                                        <tr>
                                        <td align="left">
                                        <asp:Label ID="lblColorNoteTitle" runat="server" Text="Color de nota" ></asp:Label>
                                        </td>
                                        </tr>

                                        <tr>
                                        <td>
                                        <div data-tooltip="Azul" class="tooltip-bottom" style="display: inline-block;">
                                        <asp:ImageButton ID="btn_ColorNote1" runat="server"
                                                CssClass="efecto_zoom icono_adaptable_add tooltip-bottom" 
                                                ImageUrl="~/Styles/2015/img/boton_color1.png" 
                                                CommandArgument="#ddfbf6"
                                                meta:resourcekey="ImageButton1Resource1" onclick="btn_ChangeColor_Click" />
                                        </div>

                                        <div data-tooltip="Celeste" class="tooltip-bottom" style="display: inline-block;">
                                        <asp:ImageButton ID="btn_ColorNote2" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color2.png" 
                                                CommandArgument="#e0ebf7"
                                                meta:resourcekey="ImageButton4Resource1" onclick="btn_ChangeColor_Click" />
                                        </div>

                                        <div data-tooltip="Anaranjado" class="tooltip-bottom" style="display: inline-block;">
                                        <asp:ImageButton ID="btn_ColorNote3" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color3.png" 
                                                CommandArgument="#ffefd6"
                                                meta:resourcekey="ImageButton5Resource1" onclick="btn_ChangeColor_Click" />
                                        </div>


                                        <div data-tooltip="Rojo" class="tooltip-bottom" style="display: inline-block;">
                                        <asp:ImageButton ID="btn_ColorNote4" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color4.png" 
                                                CommandArgument="#fde1e1"
                                                meta:resourcekey="ImageButton6Resource1" onclick="btn_ChangeColor_Click" />
                                        </div>

                                        <div data-tooltip="Morado" class="tooltip-bottom" style="display: inline-block;">
                                        <asp:ImageButton ID="btn_ColorNote5" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color5.png" 
                                                CommandArgument="#e9e3f6"
                                                meta:resourcekey="ImageButton7Resource1" onclick="btn_ChangeColor_Click" />
                                        </div>

                                        <div data-tooltip="Verde" class="tooltip-bottom" style="display: inline-block;">
                                        <asp:ImageButton ID="btn_ColorNote6" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color6.png" 
                                                CommandArgument="#f9fcd3"
                                                meta:resourcekey="ImageButton8Resource1" onclick="btn_ChangeColor_Click" />
                                        </div>

                                        </td>
                                        </tr>
                                    </table>


                                    <!-- Mas opciones / abrir -->
                                    <div id="tab1" class="tab_panel active" runat="server" Visible="False">
                                        <div id="seccion1" class="acordeon" style="margin-bottom:0px !important; margin-top:5px;">
                                            <div class="">
                                                <div class="colocar_derecha" style="margin-bottom:0px;">
                                                    <a class="acordeon_desplegable" data-toggle="collapse" data-parent="#seccion1" href="#seccion1_1">
                                                    <asp:Label ID="Label2" runat="server" Text="Más opciones" 
                                                        meta:resourcekey="Label2Resource1" ></asp:Label>&nbsp;&nbsp;
                                                    <asp:ImageButton ID="ImageButton2" runat="server" 
                                                        CssClass="efecto_zoom icono_adaptable_add" 
                                                        ImageUrl="~/Styles/2015/img/boton_abrir.png" 
                                                        meta:resourcekey="ImageButton2Resource1"/>
                                                    </a>
                                                </div>
                                                <div id="seccion1_1" runat="server" class="collapse" style="width:100%;">


                                                </div>
                                            </div>

                                        </div>
                                    </div>

                                        

                                  </tr>
                                  
                                  


                                </table>


                                <hr>


                                <table width="100%" border="0" align="center" cellpadding="0" cellspacing="0" >
                                  <tr>
                                    <td align="center">
                                    <div data-tooltip="Guardar Nota" class="tooltip-bottom" >
                                    <asp:ImageButton ID="btnCRMNotesSave" runat="server" CssClass="efecto_zoom icono_nota_guardar" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" 
                                    ValidationGroup="ValidateCRMNotesSave" OnClick="btnCRMNotesSave_Click" meta:resourcekey="btnCRMNotesSaveResource1" />
                                    </div>
                                    </td>

                                    <td align="center">
                                    <div data-tooltip="Enviar por SMS" class="tooltip-bottom" >
                                    <asp:ImageButton ID="btnSendNotebySMS" runat="server" 
                                            CssClass="efecto_zoom icono_nota_sms" 
                                            ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" 
                                            onclick="btnSendNotebySMS_Click"   />
                                    </div>
                                    </td>

                                    <td align="center">
                                    <div data-tooltip="Enviar por Email" class="tooltip-bottom" >
                                    <asp:ImageButton ID="btnPhoneCallSend" runat="server" CssClass="efecto_zoom icono_nota_enviar" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png"  Visible="false" />
                                    </div>
                                    </td>

                                  </tr>
                                </table>




                            </div>


                        <table width="70%" border="0" align="center" cellpadding="0" cellspacing="0" >
                        <tr>
                        <td align="center">
                        <asp:Label ID="lbMessageNotes" runat="server" CssClass="etiqueta etiqueta_azul" 
                                meta:resourcekey="lbMessageNotesResource1" ></asp:Label><br> 
                        </td>
                        </tr> 
                        </table>


            </div>


                </div>
                </div>
            </div>



        <!-- Calendario -->
        <div class="columna_ancho3">
                <div class="bloque_basico color_de_bloque">

                <div class="titulo_de_bloque2">
                    <h4></h4>
                </div>

                <div class="contenido_de_bloque" style="min-height: 360px; ">

                <!-- Agenda -->
                <div id="divCRM_Diary_List" runat="server" clientidmode="Static" >
                <h4><asp:Label ID="lblBlockTitle5lbl" runat="server" Text="Agenda" Font-Bold="True" meta:resourcekey="lblBlockTitle5lblResource1"></asp:Label></h4>
                
<%--                <div data-tooltip="Añadir evento" class="colocar_derecha tooltip-bottom" style="margin-top: -40px; " runat="server" clientidmode="Static"  meta:resourcekey="dtAddEventResource1">
                    <asp:ImageButton ID="btnAdd2" runat="server" 
                        CssClass="efecto_zoom icono_adaptable_add" 
                        ImageUrl="~/Styles/2015/img/boton_mas.png" onclick="btnCRMDiaryAdd_Click" 
                        meta:resourcekey="btnAdd2Resource1" />
                </div>--%>
                <hr>
                
                <table width="100%" border="0" align="center" cellpadding="3" cellspacing="0" >
                            <tr>
                            <td align="center">
                            <div style="border-radius:8px !important;border:2px solid #13c4a5; ">
                            <asp:Calendar ID="Calendar1" runat="server" CssClass="calendario" TabIndex="15" meta:resourcekey="Calendar1Resource1"></asp:Calendar>
                            </div>
                            </td>
                            </tr>
                </table>
               
                <hr>
                <asp:HyperLink ID="HyperLink5" runat="server" NavigateUrl="~/Modules/Calendar/CalendarDashboard.aspx" TabIndex="16" 
                CssClass="menu_tabslink_borde" >
                <asp:Label ID="Label15" runat="server" Text="Ver Agenda completa" meta:resourcekey="Label15Resource1" ></asp:Label>
                </asp:HyperLink>

                
                </div>
                


                <!-- Nueva agenda -->
               <div id="divCRM_Diary_New" runat="server" visible="False" >
                                
                    <asp:HiddenField ID="HiddenField1" runat="server" Visible="False" />
                    <h4><asp:Label ID="Label4" runat="server" Text="Nueva Agenda" Font-Bold="True" 
                            meta:resourcekey="Label4Resource1" ></asp:Label></h4>
                    <asp:Label ID="Label5" runat="server" Text="Fecha: " 
                        meta:resourcekey="Label5Resource1" ></asp:Label> <asp:Label ID="Label6" 
                        runat="server" Text="30-10-2015" ForeColor="#27C266" 
                        meta:resourcekey="Label6Resource1" ></asp:Label>
                    <div data-tooltip="Salir" class="colocar_derecha tooltip-bottom" >
                        <asp:ImageButton ID="btnCRMDiaryClose" runat="server" 
                            CssClass="efecto_zoom icono_adaptable_salir" 
                            ImageUrl="~/Styles/2015/img/boton_cerrar.png" onclick="btnCRMDiaryClose_Click" 
                            meta:resourcekey="btnCRMDiaryCloseResource1" />
                    </div>
                    <hr>
                   
                    <table width="100%" border="0" align="center" cellpadding="2" cellspacing="0" >

                        <tr>
                        <td align="right" >
                        <asp:Label ID="Label10" runat="server" Text="Asunto" 
                                meta:resourcekey="Label10Resource1" ></asp:Label>
                        </td>
                        <td>
                        <asp:TextBox ID="txtCRMDiary_Subject" runat="server" ClientIDMode="Static" 
                                CssClass="campo_texto_simple_s" MaxLength="30" 
                                meta:resourcekey="txtCRMDiary_SubjectResource1"></asp:TextBox>
                        <asp:RequiredFieldValidator ID="rfvCRMDiary_Subject" runat="server" 
                                ControlToValidate="txtCRMDiary_Subject" ErrorMessage="*" Font-Bold="True" 
                        ForeColor="Red" SetFocusOnError="True" ValidationGroup="ValidateCRMDiarySave" 
                                meta:resourcekey="rfvCRMDiary_SubjectResource1"></asp:RequiredFieldValidator>
                        </td>
                        </tr>

                        <tr>
                        <td align="right" valign="top">
                        <asp:Label ID="Label11" runat="server" Text="Descripción" 
                                meta:resourcekey="Label11Resource1" ></asp:Label>
                        </td>
                        <td>
                        <asp:TextBox ID="txtCRMDiary_Description" runat="server" ClientIDMode="Static" 
                                CssClass="campo_texto_notas_2" MaxLength="30" TextMode="MultiLine" 
                                meta:resourcekey="txtCRMDiary_DescriptionResource1"></asp:TextBox>
                        <asp:RequiredFieldValidator ID="rfvCRMDiary_Description" runat="server" 
                                ControlToValidate="txtCRMDiary_Description" ErrorMessage="*" Font-Bold="True" 
                        ForeColor="Red" SetFocusOnError="True" ValidationGroup="ValidateCRMDiarySave" 
                                meta:resourcekey="rfvCRMDiary_DescriptionResource1"></asp:RequiredFieldValidator>
                        </td>
                        </tr>

                        <tr>
                        <td align="right" colspan="2" >
                        <hr>


                        <!-- Mas opciones / abrir -->
                        <div id="Div2" class="tab_panel active">
                            <div id="Div3" class="acordeon" style="margin-bottom:0px !important; margin-top:5px;">
                                <div class="">
                                    <div class="colocar_derecha" style="margin-bottom:0px;">
                                        <a class="acordeon_desplegable" data-toggle="collapse" data-parent="#seccion1" href="#seccion1_2">
                                        <asp:Label ID="Label12" runat="server" Text="Más opciones" 
                                            meta:resourcekey="Label12Resource1" ></asp:Label>&nbsp;&nbsp;
                                        <asp:ImageButton ID="ImageButton9" runat="server" 
                                            CssClass="efecto_zoom icono_adaptable_add" 
                                            ImageUrl="~/Styles/2015/img/boton_abrir.png" 
                                            meta:resourcekey="ImageButton9Resource1"/>
                                        </a>
                                    </div>
                                    <div id="seccion1_2" class="collapse" style="width:100%;">
                                    <!-- Contenido -->    
                                    <table width="100%" border="0" align="center" cellpadding="3" cellspacing="0" >
                                        <tr>
                                        <td align="right">
                                        <asp:Label ID="Label13" runat="server" Text="Ingresado por" 
                                                meta:resourcekey="Label13Resource1" ></asp:Label>
                                        </td>
                                        <td>
                                        <asp:DropDownList ID="DropDownList3" runat="server" 
                                                CssClass="campo_texto_select_llamada" meta:resourcekey="DropDownList3Resource1">
                                        <asp:ListItem Text="Employee 1" Value="1" meta:resourcekey="ListItemResource6"></asp:ListItem>
                                        <asp:ListItem Text="Employee 2" Value="2" meta:resourcekey="ListItemResource7"></asp:ListItem>
                                        <asp:ListItem Text="Employee 3" Value="3" meta:resourcekey="ListItemResource8"></asp:ListItem>
                                        <asp:ListItem Text="Employee 4" Value="4" meta:resourcekey="ListItemResource9"></asp:ListItem>
                                        <asp:ListItem Text="Employee 5" Value="5" meta:resourcekey="ListItemResource10"></asp:ListItem>
                                            </asp:DropDownList>
                                        </td>
                                        </tr>

                                        <tr>
                                        <td align="right"><br>
                                        </td>
                                        </tr>

                                        <tr>
                                        <td align="right">
                                        <asp:Label ID="Label14" runat="server" Text="Color de nota" 
                                                meta:resourcekey="Label14Resource1" ></asp:Label>
                                        </td>
                                        <td>
                                        <asp:ImageButton ID="ImageButton10" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color1.png" 
                                                meta:resourcekey="ImageButton10Resource1" />
                                        <asp:ImageButton ID="ImageButton11" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color2.png" 
                                                meta:resourcekey="ImageButton11Resource1" />
                                        <asp:ImageButton ID="ImageButton12" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color3.png" 
                                                meta:resourcekey="ImageButton12Resource1" />
                                        <asp:ImageButton ID="ImageButton13" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color4.png" 
                                                meta:resourcekey="ImageButton13Resource1" />
                                        <asp:ImageButton ID="ImageButton14" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color5.png" 
                                                meta:resourcekey="ImageButton14Resource1" />
                                        <asp:ImageButton ID="ImageButton15" runat="server" 
                                                CssClass="efecto_zoom icono_adaptable_add" 
                                                ImageUrl="~/Styles/2015/img/boton_color6.png" 
                                                meta:resourcekey="ImageButton15Resource1" />
                                        </td>
                                        </tr>

                                    </table>

                                    </div>
                                </div>

                            </div>
                        </div>

                                        



                        </td>
                        </tr>
                                  
                                  


                    </table>


                    <hr>
                    <table width="100%" border="0" align="center" cellpadding="0" cellspacing="0" >
                        <tr>
                        <td align="center">

                        <div data-tooltip="Guardar nota" class="tooltip-bottom" >
                        <asp:ImageButton ID="btnCRMDiarySave" runat="server" 
                                CssClass="efecto_zoom icono_nota_guardar" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" 
                        ValidationGroup="ValidateCRMDiarySave" OnClick="btnCRMDiarySave_Click" 
                                meta:resourcekey="btnCRMDiarySaveResource1" />
                        </div>

                        </td>
                        </tr>
                    </table>


                </div>






                </div>
  


                </div>
            </div>


        <!-- Noticias -->
        <div class="columna_ancho3" runat="server" visible="False">
                <div class="bloque_basico color_de_bloque">

                <div class="titulo_de_bloque2">
                   
                </div>


                <div style="text-align: center;margin-top: -12px; z-index:0;  ">
                <asp:Image ID="imgNews1" runat="server" ImageUrl="~/Styles/2015/img/noticia1.jpg" 
                        class="imagen_noticias" meta:resourcekey="imgNews1Resource1"  />
                </div>   
                
                <div style="text-align: center;margin-top: -120px; z-index:10;  ">
                <asp:Image ID="IimgNews2" runat="server" 
                        ImageUrl="~/Styles/2015/img/foto_trans.png" class="imagen_noticias" 
                        meta:resourcekey="IimgNews2Resource1"  />
                </div> 

                <div style="margin-top: -42px; position:absolute; margin-left: 18px; line-height: 16px;" >
               
                <asp:Label ID="lbNewsTitle1" runat="server" 
                        Text="Ganolife te da nuevas Oportunidades" ForeColor="White" Font-Bold="True" 
                        meta:resourcekey="lbNewsTitle1Resource1" ></asp:Label>
                <br>
                <asp:Label ID="lbNewsDate1" runat="server" Text="Fecha: 14-09-2015" 
                        ForeColor="#22E06F" meta:resourcekey="lbNewsDate1Resource1" ></asp:Label>
                </div> 
           



                <div class="contenido_de_bloque" style="min-height: 50px; padding:4px !important; ">

                
                <table width="100%" border="0" align="center" cellpadding="8" cellspacing="0" class="boton_gris" style="height: 54px;">
                  <tr>
                    <td width="3%" align="left">
                    <asp:ImageButton ID="btnNews1" runat="server" 
                            ImageUrl="~/Styles/2015/img/noticia_on.png" 
                            meta:resourcekey="btnNews1Resource1" />
                    </td>

                    <td width="97%" align="left">
                    <asp:Label ID="lbNewsSubtitle1" runat="server" 
                            Text="Ganolife te da nuevas Oportunidades" 
                            meta:resourcekey="lbNewsSubtitle1Resource1" ></asp:Label>
                    </td>
                  </tr>
                </table>

                <table width="100%" border="0" align="center" cellpadding="8" cellspacing="0" class="boton_gris" style="height: 54px;">
                  <tr>
                    <td width="3%" align="left">
                    <asp:ImageButton ID="btnNews2" runat="server" 
                            ImageUrl="~/Styles/2015/img/noticia_off.png" 
                            meta:resourcekey="btnNews2Resource1" />
                    </td>

                    <td width="97%" align="left">
                    <asp:Label ID="lbNewsSubtitle2" runat="server" Text="Vida saludable con Ganolife" 
                            meta:resourcekey="lbNewsSubtitle2Resource1" ></asp:Label>
                    </td>
                  </tr>
                </table> 



                </div>
  


                </div>
            </div>


</ContentTemplate>
</asp:UpdatePanel>




        <!-- Archivos -->
        <%--<div class="columna_ancho6">
                <div class="bloque_basico color_de_bloque">
                <div class="titulo_de_bloque2"><h4></h4></div>
                <div class="contenido_de_bloque" style="min-height: 200px; ">
                <h4><asp:Label ID="lblBlockTitle6" runat="server" Text="Mis archivos" Font-Bold="True"></asp:Label></h4>               
                <div class="colocar_derecha" style="margin-top: -40px; ">
                    <asp:ImageButton ID="btnAdd3" runat="server" CssClass="efecto_zoom icono_adaptable_add" ImageUrl="~/Styles/2015/img/boton_mas.png" />
                </div>
                <hr>
                <table width="100%" border="0" align="center" cellpadding="10" cellspacing="0" class="boton_gris">
                  <tr>
                    <td width="6%" align="right">
                    <asp:Image ID="imgFile1" runat="server" ImageUrl="~/Styles/2015/img/icono_impuesto.png" />
                    </td>
                    <td width="84%" >
                    <asp:Label ID="lbFileTitle1" runat="server" Text="Documento" ></asp:Label>
                    </td>
                    <td width="10%"  align="right">
                    <asp:ImageButton ID="btnFile1" runat="server" ImageUrl="~/Styles/2015/img/icono_flecha_de.png" />
                    </td>
                  </tr>
                </table>           
                </div>
                </div>
            </div>--%>

             <!-- Ventas Region 3 -->

        <div class="columna_ancho6" id="SalesDayR3" runat="server">
                <div class="bloque_basico color_de_bloque" >

                <div class="titulo_de_bloque" style="background-color: #969696 !important;">
                <center>
                    <h4>
                    
                   <%-- <asp:Label ID="lblBlockTitle6" runat="server" Text="Ventas del día" 
                            meta:resourcekey="lblBlockTitle6Resource1" ></asp:Label>--%> 
                        <asp:Button ID="btnDailySale" runat="server" Text="Venta del día" TabIndex="17" 
                            CssClass="boton_basico boton_blanco" onclick="btnDailySale_Click"/> &nbsp;&nbsp;
                        <asp:Button ID="btnWeeklySale" runat="server" Text="Semana Actual" TabIndex="18" 
                        CssClass="boton_basico boton_blanco" onclick="btnWeeklySale_Click" /> &nbsp;&nbsp;
                          <asp:Button ID="btnLastWeeklySale" runat="server" Text="Últimos 7 dias" TabIndex="19" 
                        CssClass="boton_basico boton_blanco" onclick="btnLastWeeklySale_Click"  />
                      
                            </h4> 
                            </center>      
                </div>

                <div class="contenido_de_bloque" style="min-height: 300px; ">

                <div style="min-height: 245px; margin-left:30px;" id="divDailySales" runat="server" clientidmode="Static">
                <iframe src="Modules/Reports/Dashboard/BarDashboard.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
              </div>

                 <div style="min-height: 245px; margin-left:30px;" id="divWeeklySales" runat="server" clientidmode="Static"  >
                <iframe src="Modules/Reports/Dashboard/BarDashboardWeeklySale.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
              </div>

                <div style="min-height: 245px; margin-left:30px;" id="divLastWeeklySales" runat="server" clientidmode="Static"  >
                <iframe src="Modules/Reports/Dashboard/BarDashboardLastWeeklySale.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
              </div>

                </div>            

                </div>
        </div>

          <!-- Ventas Peru -->
         <div class="columna_ancho6" id="SalesDayPE" runat="server">

           <div class="bloque_basico color_de_bloque" >

                <div class="titulo_de_bloque" style="background-color: #969696 !important;">
                <center>
                    <h4>
                        <asp:Label ID="Label8" runat="server" Text="Ventas de las Sucursales" Font-Bold="True"></asp:Label>
                        <asp:Label ID="Label16" runat="server" Text="" Width="50px"></asp:Label>
                        <asp:Button ID="btnSalesDayPE" runat="server" Text="Por Fecha" TabIndex="17" 
                        CssClass="boton_basico boton_blanco" onclick="btnSalesDayPE_Click"  /> &nbsp;&nbsp;
                        <asp:Button ID="btnSalesWeekPE" runat="server" Text="Semana Actual" TabIndex="18" 
                        CssClass="boton_basico boton_blanco" onclick="btnSalesWeekPE_Click"  /> &nbsp;&nbsp;

                    </h4>
                    </center>
                </div>

                <div class="contenido_de_bloque" style="min-height: 300px; ">

                <div style="min-height: 245px; margin-left:30px;" id="DivSalesDayPE" runat="server" clientidmode="Static">
                <iframe src="Modules/Reports/Dashboard/PE/SalesDay.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
                </div>

                <div style="min-height: 245px; margin-left:30px;" id="DivWeeklyPE" runat="server" clientidmode="Static">
                <iframe src="Modules/Reports/Dashboard/PE/Weekly.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
                </div>

                 <div style="min-height: 245px; margin-left:30px;" id="DivSalesDayMiraflores" runat="server" clientidmode="Static">
                <iframe src="Modules/Reports/Dashboard/PE/SalesDaybyWarehouse1.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
                </div>

                 <div style="min-height: 245px; margin-left:30px;" id="DivSalesDayOlivos" runat="server" clientidmode="Static">
                <iframe src="Modules/Reports/Dashboard/PE/SalesDaybyWarehouse3.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
                </div>

                 <div style="min-height: 245px; margin-left:30px;" id="DivWeeklyMiraflores" runat="server" clientidmode="Static">
                <iframe src="Modules/Reports/Dashboard/PE/WeeklybyWarehouse1.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
                </div>

                 <div style="min-height: 245px; margin-left:30px;" id="DivWeeklyOlivos" runat="server" clientidmode="Static">
                <iframe src="Modules/Reports/Dashboard/PE/WeeklybyWarehouse3.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
                </div>

                

                </div>
                </div>
         </div>

           <!-- Ventas El Salvador -->
         <div class="columna_ancho6" id="SalesDaySV" runat="server">

           <div class="bloque_basico color_de_bloque" >

                <div class="titulo_de_bloque" style="background-color: #969696 !important;">
                <center>
                    <h4>
                        <asp:Label ID="Label9" runat="server" Text="Ventas de las Sucursales" Font-Bold="True"></asp:Label>
                        <asp:Label ID="Label17" runat="server" Text="" Width="50px"></asp:Label>
                        <asp:Button ID="btnSalesSV" runat="server" Text="Por Fecha" TabIndex="17" 
                        CssClass="boton_basico boton_blanco" onclick="btnSalesDaySV_Click"  /> &nbsp;&nbsp;
                        <asp:Button ID="btnSalesWeekSV" runat="server" Text="Semana Actual" TabIndex="18" 
                        CssClass="boton_basico boton_blanco" onclick="btnSalesWeekSV_Click"  /> &nbsp;&nbsp;
                    </h4>
                    </center>
                </div>

                <div class="contenido_de_bloque" style="min-height: 300px; ">

                
                <div style="min-height: 245px; margin-left:30px;" id="DivSalesDaySV" runat="server" clientidmode="Static">
                <iframe src="Modules/Reports/Dashboard/SV/SalesDay.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
              </div>

                 <div style="min-height: 245px; margin-left:30px;" id="DivWeeklySV" runat="server" clientidmode="Static">
                <iframe src="Modules/Reports/Dashboard/SV/Weekly.aspx" width="100%" height="300" frameBorder="0" scrolling = "no" 
                allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
                </div>



                </div>
                </div>
         </div>

        </div>



        <!-- Bloque Ocultos -->

        <div class="fila-ajustable aparecer" style="display: none;"> 

        <!-- Escrbir Nota-->
        <div class="columna_ancho3">
                <div class="bloque_basico color_de_bloque">

                <div class="titulo_de_bloque2">
                    <h4></h4>
                </div>

                <div class="contenido_de_bloque" style="min-height: 270px; ">
        
                <h4><asp:Label ID="lblBlockTitle7" runat="server" Text="Nueva Nota" 
                        Font-Bold="True" meta:resourcekey="lblBlockTitle7Resource1" ></asp:Label></h4>
                
                <div class="colocar_derecha" style="margin-top: -16px; ">
                    <asp:ImageButton ID="btnClose1" runat="server" 
                        CssClass="efecto_zoom icono_adaptable_salir" 
                        ImageUrl="~/Styles/2015/img/boton_cerrar.png" 
                        meta:resourcekey="btnClose1Resource1" />
                </div>
                <hr>
                
                <div class="colocar_derecha" >
                    <asp:Label ID="lbNoteDate" runat="server" Text="Fecha" ForeColor="#27C266" meta:resourcekey="lbNoteDateResource1" ></asp:Label>
                </div>


                <br><br>
                   
                <table width="90%" border="0" align="center" cellpadding="0" cellspacing="0" >
                  <tr>
                    <td >
                    <asp:Label ID="lbNoteText" runat="server" Text="Contenido de la nota" meta:resourcekey="lbNoteTextResource1" ></asp:Label>
                    </td>
                  </tr>
                </table>

                <hr>
                <table width="100%" border="0" align="center" cellpadding="0" cellspacing="0" >
                  <tr>
                    <td align="center">
                    <asp:ImageButton ID="btnNoteSave" runat="server" CssClass="icono_nota_guardar" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" meta:resourcekey="btnNoteSaveResource1" />
                    </td>

                    <td align="center">
                    <asp:ImageButton ID="btnNoteSend" runat="server" CssClass="icono_nota_enviar" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" meta:resourcekey="btnNoteSendResource1" />
                    </td>

                    <td align="center">
                    <asp:ImageButton ID="btnNoteDelete" runat="server" CssClass="icono_nota_borrar" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" meta:resourcekey="btnNoteDeleteResource1" />
                    </td>
                  </tr>
                </table>


                </div>
  


                </div>
            </div>


        <!-- Calendario -->
        <div class="columna_ancho3">
                <div class="bloque_basico color_de_bloque">

                <div class="titulo_de_bloque2"><h4></h4></div>

                <div class="contenido_de_bloque" style="min-height: 270px; ">
                <h4><asp:Label ID="lblBlockTitle8" runat="server" Text="Agregar evento" Font-Bold="True" meta:resourcekey="lblBlockTitle8Resource1" ></asp:Label></h4>
                
                <div class="colocar_derecha" style="margin-top: -16px; ">
                    <asp:ImageButton ID="btnClose2" runat="server" CssClass="efecto_zoom icono_adaptable_salir" ImageUrl="~/Styles/2015/img/boton_cerrar.png" meta:resourcekey="btnClose2Resource1" />
                </div>
                <hr>
                
                <div class="controles-grupales texto_centrado">
                <asp:TextBox ID="txtSelectDate" runat="server" ClientIDMode="Static" CssClass="campo_texto_ingresarfecha" 
                data-toggle="tooltip" data-placement="right" title="Seleccione una Fecha" placeholder="Fecha" meta:resourcekey="txtSelectDateResource1"></asp:TextBox>
                </div>
                <br>

                <table width="90%" border="0" align="center" cellpadding="0" cellspacing="0" >
                  <tr>
                    <td >
                    <asp:Label ID="lbDateText1" runat="server" Text="Contenido del evento" meta:resourcekey="lbDateText1Resource1" ></asp:Label>
                    </td>
                  </tr>

                </table>
           
                <hr>
                <table width="100%" border="0" align="center" cellpadding="0" cellspacing="0" >
                  <tr>
                    <td align="center">
                    <asp:ImageButton ID="btnSave2" runat="server" CssClass="icono_nota_guardar" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" meta:resourcekey="btnSave2Resource1" />
                    </td>

                    <td align="center">
                    <asp:ImageButton ID="btnSend2" runat="server" CssClass="icono_nota_enviar" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" meta:resourcekey="btnSend2Resource1" />
                    </td>

                    <td align="center">
                    <asp:ImageButton ID="btnDelete2" runat="server" CssClass="icono_nota_borrar" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" meta:resourcekey="btnDelete2Resource1" />
                    </td>
                  </tr>
                </table>


                </div>
  

                </div>
            </div>



        <!-- Archivos -->
        <div class="columna_ancho3 ">
                <div class="bloque_basico color_de_bloque">

                <div class="titulo_de_bloque2"><h4></h4></div>

                <div class="contenido_de_bloque" style="min-height: 200px; ">
                <h4><asp:Label ID="lblBlockTitle9" runat="server" Text="Subir archivos" Font-Bold="True" meta:resourcekey="lblBlockTitle9Resource1"></asp:Label></h4>
                
                <div class="colocar_derecha" style="margin-top: -16px; ">
                    <asp:ImageButton ID="btnClose3" runat="server" CssClass="efecto_zoom icono_adaptable_salir" ImageUrl="~/Styles/2015/img/boton_cerrar.png" meta:resourcekey="btnClose3Resource1" />
                </div>
                <hr>

                <div class="controles-grupales texto_centrado">
                <asp:TextBox ID="txtSelectDFile" runat="server" ClientIDMode="Static" CssClass="campo_texto_carpeta" 
                data-toggle="tooltip" data-placement="right" title="Seleccionar archiv" placeholder="Seleccionar archivo" meta:resourcekey="txtSelectDFileResource1"></asp:TextBox>
                </div>
                <br>

                <table width="100%" border="0" align="center" cellpadding="0" cellspacing="0" >
                  <tr>

                    <td align="center">
                    <asp:ImageButton ID="btnUpload1" runat="server" CssClass="icono_nota_subir" ImageUrl="~/Styles/2015/img/icono_nota_espacio.png" meta:resourcekey="btnUpload1Resource1" />
                    </td>
                  </tr>
                </table>

                </div>

                </div>
            </div>

        </div>


        <!-- Bloque Dashboard CRM -->
        <div style="display: none;" >

        <br><br><br>/ / / / / / / / / / / / / / / / / / / / / / / / / / / /  Dashboard CRM   / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / / <br><br><br><br>
        
        <div class="fila-ajustable aparecer" >
        
              <div class="columna_ancho12" >
              <h2><asp:Image ID="imgTitle" runat="server" 
                      ImageUrl="~/Styles/2015/img/modulo_color_crm.png" style="margin-right: 10px; " 
                      meta:resourcekey="imgTitleResource1" /><asp:Label ID="lblPageTitle2" 
                      runat="server" Text="CRM" meta:resourcekey="lblPageTitle2Resource1" ></asp:Label></h2>
              <hr>
              <div style="margin-top: -10px; ">
              <asp:Label ID="lbPageLink1" runat="server"  CssClass="texto_gris" Text="Inicio" 
                      meta:resourcekey="lbPageLink1Resource1" ></asp:Label>
              <asp:Label ID="lblLine1" runat="server"  CssClass="texto_gris" 
                      Text="&nbsp;&nbsp;/&nbsp;&nbsp;" meta:resourcekey="lblLine1Resource1" ></asp:Label>
              <asp:Label ID="lbPageLink2" runat="server"  CssClass="texto_gris" Text="CRM" 
                      meta:resourcekey="lbPageLink2Resource1" ></asp:Label>
              <asp:Label ID="lblLine2" runat="server"  CssClass="texto_gris" 
                      Text="&nbsp;&nbsp;/&nbsp;&nbsp;" meta:resourcekey="lblLine2Resource1" ></asp:Label>
              <asp:Label ID="lbPageLink3" runat="server"  CssClass="texto_gris" Text="Clientes" 
                      ForeColor="#FFA302" meta:resourcekey="lbPageLink3Resource1"></asp:Label>
              </div>
              <br><br>
              </div>
        </div>
              


        <div class="fila-ajustable" >
        
        <!-- Nuevo cliente -->
        <div class="columna_ancho4">
                <div class="bloque_basico color_de_bloque color_crm_clientes">

                <div class="titulo_de_bloque2"><h4></h4></div>
                
                <div class="contenido_de_bloque" style="min-height: 120px; border: 0px solid #ffa600 !important;">
                    <div class="colocar_derecha" >
                        <asp:ImageButton ID="btnAdd4" runat="server" CssClass="efecto_zoom" 
                            ImageUrl="~/Styles/2015/img/boton_mas.png" 
                            meta:resourcekey="btnAdd4Resource1" />
                    </div>
                
                    <div class="colocar_izquierda" >
                        <asp:Image ID="imgIcon1" runat="server" 
                            ImageUrl="~/Styles/2015/img/icono_nuevocliente.png" 
                            meta:resourcekey="imgIcon1Resource1" />
                    </div><br><br><br>
                    <h4><asp:Label ID="lblTitle1" runat="server" Text="Nuevo Cliente" Font-Bold="True" 
                            meta:resourcekey="lblTitle1Resource1" ></asp:Label></h4>
                </div>

                </div>
        </div>

        <!-- Editar cliente -->
        <div class="columna_ancho4">
                <div class="bloque_basico color_de_bloque color_crm_editar">

                <div class="titulo_de_bloque2" style="background-color:#5191d1 !important"><h4></h4></div>
                
                <div class="contenido_de_bloque" style="min-height: 120px; border: 0px solid #ffa600 !important;">
                    <div class="colocar_derecha" >
                        <asp:ImageButton ID="btnAdd5" runat="server" CssClass="efecto_zoom" 
                            ImageUrl="~/Styles/2015/img/boton_mas.png" 
                            meta:resourcekey="btnAdd5Resource1" />
                    </div>
                
                    <div class="colocar_izquierda" >
                        <asp:Image ID="imgIcon2" runat="server" 
                            ImageUrl="~/Styles/2015/img/icono_editarcliente.png" 
                            meta:resourcekey="imgIcon2Resource1" />
                    </div><br><br><br>
                    <h4><asp:Label ID="lblTitle2" runat="server" Text="Nuevo Cliente" Font-Bold="True" 
                            meta:resourcekey="lblTitle2Resource1" ></asp:Label></h4>
                </div>

                </div>
        </div>

        <!-- Notes -->
        <div class="columna_ancho4">
                <div class="bloque_basico color_de_bloque color_crm_tickets">

                <div class="titulo_de_bloque2" style="background-color:#7c53da !important"><h4></h4></div>
                
                <div class="contenido_de_bloque" style="min-height: 120px; border: 0px solid #ffa600 !important;">
                    <div class="colocar_derecha" >
                        <asp:ImageButton ID="btnAdd6" runat="server" CssClass="efecto_zoom" 
                            ImageUrl="~/Styles/2015/img/boton_mas.png" 
                            meta:resourcekey="btnAdd6Resource1" />
                    </div>
                
                    <div class="colocar_izquierda" >
                        <asp:Image ID="imgIcon3" runat="server" 
                            ImageUrl="~/Styles/2015/img/icono_tickets.png" 
                            meta:resourcekey="imgIcon3Resource1" />
                    </div><br><br><br>
                    <h4><asp:Label ID="lblTitle3" runat="server" Text="Nuevo Cliente" Font-Bold="True" 
                            meta:resourcekey="lblTitle3Resource1" ></asp:Label></h4>
                </div>

                </div>
        </div>
        </div>



        <div class="fila-ajustable" >

        <!-- Pedidos -->
        <div class="columna_ancho4">
                <div class="bloque_basico color_de_bloque color_crm_pedidos">

                <div class="titulo_de_bloque2" style="background-color:#ef4db6 !important"><h4></h4></div>
                
                <div class="contenido_de_bloque" style="min-height: 120px; border: 0px solid #ffa600 !important;">
                    <div class="colocar_derecha" >
                        <asp:ImageButton ID="btnAdd7" runat="server" CssClass="efecto_zoom" 
                            ImageUrl="~/Styles/2015/img/boton_mas.png" 
                            meta:resourcekey="btnAdd7Resource1" />
                    </div>
                
                    <div class="colocar_izquierda" >
                        <asp:Image ID="imgIcon4" runat="server" 
                            ImageUrl="~/Styles/2015/img/icono_pedidos.png" 
                            meta:resourcekey="imgIcon4Resource1" />
                    </div><br><br><br>
                    <h4><asp:Label ID="lblTitle4" runat="server" Text="Nuevo Cliente" Font-Bold="True" 
                            meta:resourcekey="lblTitle4Resource1" ></asp:Label></h4>
                </div>

                </div>
        </div>

        <!-- Fidelización -->
        <div class="columna_ancho4">
                <div class="bloque_basico color_de_bloque color_crm_fidelizacion">

                <div class="titulo_de_bloque2" style="background-color:#959595 !important"><h4></h4></div>
                
                <div class="contenido_de_bloque" style="min-height: 120px; border: 0px solid #ffa600 !important;">
                    <div class="colocar_derecha" >
                        <asp:ImageButton ID="btnAdd8" runat="server" CssClass="efecto_zoom" 
                            ImageUrl="~/Styles/2015/img/boton_mas.png" 
                            meta:resourcekey="btnAdd8Resource1" />
                    </div>
                
                    <div class="colocar_izquierda" >
                        <asp:Image ID="imgIcon5" runat="server" 
                            ImageUrl="~/Styles/2015/img/icono_fidelizacion.png" 
                            meta:resourcekey="imgIcon5Resource1" />
                    </div><br><br><br>
                    <h4><asp:Label ID="lblTitle5" runat="server" Text="Fidelización" Font-Bold="True" 
                            meta:resourcekey="lblTitle5Resource1" ></asp:Label></h4>
                </div>

                </div>
        </div>

        <!-- LLamadas -->
        <div class="columna_ancho4">
                <div class="bloque_basico color_de_bloque color_crm_llamadas">

                <div class="titulo_de_bloque2" style="background-color:#f95252 !important"><h4></h4></div>
                
                <div class="contenido_de_bloque" style="min-height: 120px; border: 0px solid #ffa600 !important;">
                    <div class="colocar_derecha" >
                        <asp:ImageButton ID="btnAdd9" runat="server" CssClass="efecto_zoom" 
                            ImageUrl="~/Styles/2015/img/boton_mas.png" 
                            meta:resourcekey="btnAdd9Resource1" />
                    </div>
                
                    <div class="colocar_izquierda" >
                        <asp:Image ID="imgIcon6" runat="server" 
                            ImageUrl="~/Styles/2015/img/icono_llamadas.png" 
                            meta:resourcekey="imgIcon6Resource1" />
                    </div><br><br><br>
                    <h4><asp:Label ID="lblTitle6" runat="server" Text="Llamadas" Font-Bold="True" 
                            meta:resourcekey="lblTitle6Resource1" ></asp:Label></h4>
                </div>

                </div>
        </div>

        </div>



        <!-- Checkbox -->
        <div class="fila-ajustable" >

        <div class="columna_ancho4">
        <div class="bloque_basico color_de_bloque ">
        <div class="contenido_de_bloque" >
        <br><br>
        <div class="wrapper">
          <input type="checkbox" name="toggle" id="toggle">
          <label for="toggle"></label>
        </div>

        <br><br>

        <div class="wrapper">
          <input type="checkbox" name="toggle2" id="toggle2">
          <label for="toggle2"></label>
        </div>
        <br><br>
        </div>
        </div>
        </div>

        </div>

        </div>



</div>
</div>


</div>



<!-- /Contenedor principal -->

<%--    <script type='text/javascript'>
        LastVersion('<%= System.Configuration.ConfigurationManager.AppSettings["WebVersion"] %>');
    </script>--%>



</asp:Content>
