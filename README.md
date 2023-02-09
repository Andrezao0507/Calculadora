# Calculadora
unit Unit1;

interface

uses
  Winapi.Windows, Winapi.Messages, System.SysUtils, System.Variants, System.Classes, Vcl.Graphics,
  Vcl.Controls, Vcl.Forms, Vcl.Dialogs, Vcl.Buttons, Vcl.StdCtrls, Vcl.ExtCtrls;

type
  TForm1 = class(TForm)
    EdtVisor: TEdit;
    SpeedButtonUm: TSpeedButton;
    SpeedButtonMais: TSpeedButton;
    SpeedButtonTres: TSpeedButton;
    SpeedButtonDois: TSpeedButton;
    SpeedButtonMaismenos: TSpeedButton;
    SpeedButtonSeis: TSpeedButton;
    SpeedButtonCinco: TSpeedButton;
    SpeedButtonQuatro: TSpeedButton;
    SpeedButtonMultiplicar: TSpeedButton;
    SpeedButtonDividir: TSpeedButton;
    SpeedButtonVirgula: TSpeedButton;
    SpeedButtonMenos: TSpeedButton;
    SpeedButtonNove: TSpeedButton;
    SpeedButtonOito: TSpeedButton;
    SpeedButtonSete: TSpeedButton;
    SpeedButtonLimpar: TSpeedButton;
    SpeedButtonZero: TSpeedButton;
    SpeedButtonIgual: TSpeedButton;
    procedure SpeedButtonUmClick(Sender: TObject);
    procedure SpeedButtonMaisClick(Sender: TObject);
    procedure SpeedButtonMenosClick(Sender: TObject);
    procedure SpeedButtonDividirClick(Sender: TObject);
    procedure SpeedButtonMultiplicarClick(Sender: TObject);
    procedure SpeedButtonMaismenosClick(Sender: TObject);
    procedure SpeedButtonVirgulaClick(Sender: TObject);
    procedure SpeedButtonLimparClick(Sender: TObject);
    procedure SpeedButtonIgualClick(Sender: TObject);
    procedure FormShow(Sender: TObject);
    procedure FormKeyDown(Sender: TObject; var Key: Word; Shift: TShiftState);
  private
    { Private declarations }
  public
    { Public declarations }
  end;

var
  Form1: TForm1;
  valor1:real;
  valor2:real;
  funçao: integer;

implementation

{$R *.dfm}

procedure TForm1.FormKeyDown(Sender: TObject; var Key: Word;
  Shift: TShiftState);
begin
 if Key = VK_NUMPAD1 then
    SpeedButtonum.Click;
  if Key = VK_NUMPAD2 then
    SpeedButtondois.click;
  if Key = VK_NUMPAD3 then
    SpeedButtontres.click;
  if Key = VK_NUMPAD4 then
    SpeedButtonquatro.click;
  if Key = VK_NUMPAD5 then
    SpeedButtonCinco.click;
  if Key = VK_NUMPAD6 then
    SpeedButtonseis.click;
  if Key = VK_NUMPAD7 then
    SpeedButtonsete.click;
  if Key = VK_NUMPAD8 then
    SpeedButtonoito.click;
  if Key = VK_NUMPAD9 then
    SpeedButtonnove.click;
  if Key = VK_NUMPAD0 then
    SpeedButtonzero.click;
  if Key = VK_ADD then
    SpeedButtonmais.click;
  if Key = VK_SUBTRACT then
    SpeedButtonmenos.click;
  if Key = VK_MULTIPLY then
    SpeedButtonmultiplicar.click;
  if Key = VK_DIVIDE then
    SpeedButtondividir.click;
  if Key = VK_RETURN then
    SpeedButtonigual.click;
  if Key = VK_DECIMAL then
    SpeedButtonvirgula.Click;
  if Key = VK_DELETE then
    SpeedButtonlimpar.click;

end;

procedure TForm1.FormShow(Sender: TObject);
begin
Valor1 := 0;
  valor2 := 0;
end;

procedure TForm1.SpeedButtonDividirClick(Sender: TObject);
begin
  valor1 := StrToFloat(EdtVisor.Text);
  EdtVisor.Text := '';
  funçao := 4;

end;

procedure TForm1.SpeedButtonIgualClick(Sender: TObject);
var
soma: real;
begin
  valor2:=StrToFloat(EdtVisor.Text);
  case (funçao) of
  1:
  begin
    soma:=valor1+valor2;
    EdtVisor.text:=FloatToStr(soma);
end;
    2:
  begin
    soma:=valor1-valor2;
    EdtVisor.text:=FloatToStr(soma);
  end;
  3:
  begin
    soma:=valor1*valor2;
    EdtVisor.text:=FloatToStr(soma);
  end;
  4:
  begin
    if(valor2<>0)then
      begin
        soma:=valor1/valor2;
        EdtVisor.text:=FloatToStr(soma);
      end
    else
      begin
        ShowMessage('Divisão por zero!!');
        EdtVisor.Text:='ERRO';
      end
    end
end;  //finaliza o  case
if (valor2 <> 0) then
    valor1 := StrToFloat(EdtVisor.Text);
end;

procedure TForm1.SpeedButtonLimparClick(Sender: TObject);
begin
EdtVisor.Text:='';
end;

procedure TForm1.SpeedButtonMaisClick(Sender: TObject);
begin
    valor1 := StrToFloat(EdtVisor.Text);
  EdtVisor.Text := '';
  funçao := 1;
end;

procedure TForm1.SpeedButtonMaismenosClick(Sender: TObject);
begin
EdtVisor.Text:='-'+EdtVisor.Text;
end;

procedure TForm1.SpeedButtonMenosClick(Sender: TObject);
begin
  valor1 := StrToFloat(EdtVisor.Text);
  EdtVisor.Text := '';
  funçao := 2;
end;

procedure TForm1.SpeedButtonMultiplicarClick(Sender: TObject);
begin
 valor1 := StrToFloat(EdtVisor.Text);
  EdtVisor.Text := '';
  funçao := 3;

end;

procedure TForm1.SpeedButtonUmClick(Sender: TObject);
begin
  EdtVisor.Text := EdtVisor.Text + (Sender as TSpeedButton).Caption
end;

procedure TForm1.SpeedButtonVirgulaClick(Sender: TObject);
begin
  valor1 := StrToFloat(EdtVisor.Text);
  EdtVisor.Text := EdtVisor.Text + ',';
  funçao := 2;
end;

end. 
