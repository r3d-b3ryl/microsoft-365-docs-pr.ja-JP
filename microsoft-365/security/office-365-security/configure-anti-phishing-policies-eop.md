---
title: EOP で既定のフィッシング対策ポリシーを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online メールボックスを使用して、Office 365 組織の既定のフィッシング対策ポリシーで利用可能なスプーフィング対策設定を変更する方法を学習できます。
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537535"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a>EOP で既定のフィッシング対策ポリシーを構成する

Exchange online メールボックスを使用しない exchange online メールボックスおよびスタンドアロンの Exchange Online Protection (EOP) 組織を使用している Office 365 組織には、既定のフィッシング対策ポリシーがあります。 このポリシーには、既定で有効になっている、限られた数のスプーフィング対策機能が含まれています。 詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。

Office 365 Exchange Online メールボックスを使用する組織では、Office 365 セキュリティ & コンプライアンスセンターまたは Exchange Online PowerShell で既定のフィッシング対策ポリシーを変更できます。 Exchange Online メールボックスを使用しないスタンドアロン EOP 組織では、既定のフィッシング対策ポリシーを変更することはできません。

Office 365 Advanced Threat Protection で使用可能な、より高度な ATP のフィッシング対策ポリシーの作成と変更の詳細については、「 [office 365 で ATP のフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **フィッシング対策**ページに直接移動するには、を<https://protection.office.com/antiphishing>使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 フィッシング対策ポリシーを追加、変更、および削除するには、**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。 フィッシング対策ポリシーに対する読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。 セキュリティ/コンプライアンス センターの役割グループの詳細については、「[Office 365 セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。

- 既定のフィッシング対策ポリシーの推奨設定については、「 [EOP default フィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)」を参照してください。

- 更新されたポリシーが適用されるまで最大30分かかります。

- フィルタリングパイプラインにフィッシング対策ポリシーを適用する方法については、「 [Office 365 での電子メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>セキュリティ & コンプライアンスセンターを使用して既定のフィッシング対策ポリシーを変更する

既定のフィッシング対策ポリシーの名前は、Office365 フィッシング対策 Default で、ポリシーの一覧には表示されません。 既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>の**フィッシング対策**] に移動します。

2. [**フィッシング対策**] ページで、[**既定のポリシー**] をクリックします。

3. [**ポリシーの Office 365 フィッシング対策の既定の編集**] ページが表示されます。 [**スプーフィング**] セクションで、[**編集**] をクリックします。

   これらの設定は、ATP のフィッシング対策ポリシーで使用可能なスプーフィング設定と同じであることに注意してください。

   - **フィルター設定のスプーフィング**: 既定値は**on**で、そのままにすることをお勧めします。 この機能をオフにするには、トグルを [**オフ**] にします。 詳細については、「 [Configure スプーフ知能 In Office 365](learn-about-spoof-intelligence.md)」を参照してください。

     > [!NOTE]
     > MX レコードが Office 365 を指していない場合は、スプーフィング対策保護を無効にする必要はありません。代わりに、コネクタの拡張フィルターを有効にします。 手順については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。

   - [認証されていない**送信者機能を有効にする**]: メッセージが電子メール認証チェックに失敗した場合に、送信者の写真に疑問符を追加します。 詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。 既定値は [**オン**] です。 この機能をオフにするには、トグルを [**オフ**] にします。

   - **アクション**: スプーフィングインテリジェンスに失敗したメッセージに対して実行するアクションを指定します。

     **ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信**される場合:

     - **受信者の迷惑メールフォルダーにメッセージを移動**します (これは既定値です)。
     - **メッセージを検疫する**

   - **設定を確認**します。個々の手順をクリックする代わりに、設定が概要で表示されます。

     - 各セクションで [**編集**] をクリックすると、関連するページに戻ることができます。
     - このページでは、次の設定の**オン**と**オフ**を直接切り替えることができます。

       - **スプーフィング対策保護を有効にする**
       - **認証されていない送信者機能を有効にする**

   完了したら、[任意のページに**保存**] をクリックします。

4. [Policy を**編集する Office365 フィッシング対策 Default** ] ページに戻り、設定を確認してから [**閉じる**] をクリックします。

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a>セキュリティ & コンプライアンスセンターを使用して既定のフィッシング対策ポリシーを表示する

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。

2. [**既定のポリシー** ] をクリックして、既定のフィッシング対策ポリシーを表示します。

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a>Exchange Online の PowerShell を使用して既定のフィッシング対策ポリシーを構成する

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a>PowerShell を使用して既定のフィッシングポリシーを表示する

既定のフィッシングポリシーを表示するには、次のコマンドを実行します。

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)」を参照してください。

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a>PowerShell を使用して既定のフィッシングポリシーを変更する

既定のフィッシングポリシーを変更するには、次の構文を使用します。

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

この例では、認証チェックに失敗したスプーフィングされたメッセージに対するアクションを、検疫に変更します。

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

既定のフィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。

- [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>の**フィッシング** \>対策] に移動し、[**既定のポリシー** ] をクリックして、フライアウトの詳細を表示します。

- Exchange Online PowerShell で次のコマンドを実行し、設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
