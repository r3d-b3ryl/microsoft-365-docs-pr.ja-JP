---
title: ドキュメント フィンガープリントについて
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
ms.localizationpriority: medium
description: 組織内のインフォメーション ワーカーは、日常的にさまざまな種類の機密情報を処理します。 ドキュメント フィンガープリンティングは、組織全体で使用される標準フォームを特定することによってこの情報の保護を容易にします。 このトピックでは、ドキュメント フィンガープリントの背後にある概念と、PowerShell を使用してドキュメント フィンガープリントを作成する方法について説明します。
ms.openlocfilehash: 1ad29126783b9d824789b06020b8f925be00ffbb
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66627627"
---
# <a name="document-fingerprinting"></a>ドキュメント フィンガープリンティング

組織内のインフォメーション ワーカーは、日常的にさまざまな種類の機密情報を処理します。 Microsoft Purview コンプライアンス ポータルでは、ドキュメント フィンガープリントを使用すると、組織全体で使用される標準フォームを識別することで、この情報を簡単に保護できます。 このトピックでは、ドキュメント フィンガープリントの背後にある概念と、PowerShell を使用してドキュメント フィンガープリントを作成する方法について説明します。

## <a name="basic-scenario-for-document-fingerprinting"></a>ドキュメント フィンガープリンティングに関する基本的なシナリオ

ドキュメント フィンガープリントは、標準フォームを機密情報の種類に変換するMicrosoft Purview データ損失防止 (DLP) 機能で、DLP ポリシーのルールで使用できます。 たとえば、空のパテント テンプレートに基づいてドキュメント フィンガープリントを作成し、機密コンテンツが入力されているすべての送信パテント テンプレートを検出してブロックする DLP ポリシーを作成できます。 必要に応じて、機密情報を送信している可能性があることを送信者に通知する [ポリシー ヒント](use-notifications-and-policy-tips.md) を設定できます。送信者は、受信者が特許を受ける資格があることを確認する必要があります。 このプロセスは、組織内で使用されているテキストベースのフォームで動作します。 アップロードできるフォームのその他の例を次に示します。

- 政府機関フォーム
- Health Insurance Portability and Accountability Act (HIPAA) 準拠フォーム
- 人事部門の従業員情報フォーム
- 組織用に特別に作成されたカスタム フォーム

組織で機密情報を送信するときに特定のフォームを使用するという業務習慣が既に確立されていることが理想的です。 ドキュメント フィンガープリントに変換する空のフォームをアップロードし、対応するポリシーを設定すると、DLP はその指紋に一致する送信メール内のすべてのドキュメントを検出します。

## <a name="how-document-fingerprinting-works"></a>ドキュメント フィンガープリンティングのしくみ

ドキュメントに実際の指紋があるわけではありませんが、名前からその機能を想像することができます。 人間の指紋に固有のパターンがあるように、ドキュメントにも固有の単語パターンがあります。 ファイルをアップロードすると、DLP はドキュメント内の一意の単語パターンを識別し、そのパターンに基づいてドキュメント フィンガープリントを作成し、そのドキュメント フィンガープリントを使用して同じパターンを含む送信ドキュメントを検出します。 これにより、フォームまたはテンプレートをアップロードすると、ドキュメント フィンガープリントの最も有効なタイプが作成されます。 フォームに記入するユーザーは全員同じオリジナルの単語セットを使用し、その上で独自の単語をドキュメントに追加します。 送信ドキュメントがパスワードで保護されておらず、元のフォームのすべてのテキストが含まれている限り、DLP はドキュメントがドキュメントフィンガープリントと一致するかどうかを判断できます。

> [!IMPORTANT]
> 現時点では、DLP では、Exchange Online でのみ、ドキュメント フィンガープリントを検出方法として使用できます。

次の例では、特許情報テンプレートに基づいてドキュメント フィンガープリントを作成した場合に何が行われるかを示しています。ただし、ドキュメント フィンガープリントは、任意のフォームに基づいて作成できます。

### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>特許情報テンプレートのドキュメント フィンガープリントと一致する特許情報ドキュメントの例

![ドキュメント フィンガープリントの図。](../media/Document-Fingerprinting-diagram.png)

パテント テンプレートには、"Patent title"、"発明者"、および "Description" という空白のフィールドと、それらの各フィールドの説明が含まれています。これはワード パターンです。 元のパテント テンプレートをアップロードすると、サポートされているファイルの種類の 1 つとプレーンテキストになります。 DLP は、このワード パターンをドキュメント フィンガープリントに変換します。これは、元のテキストを表す一意のハッシュ値を含む小さな Unicode XML ファイルであり、指紋は Active Directory のデータ分類として保存されます。 (セキュリティ対策として、元のドキュメント自体はサービスに格納されません。ハッシュ値のみが格納され、元のドキュメントをハッシュ値から再構築することはできません)。その後、パテント フィンガープリントは機密情報の種類になり、DLP ポリシーに関連付けることができます。 DLP ポリシーに指紋を関連付けた後、DLP は、パテント フィンガープリントと一致するドキュメントを含む送信電子メールを検出し、組織のポリシーに従って処理します。

たとえば、通常の従業員がパテントを含む送信メッセージを送信できないようにする DLP ポリシーを設定できます。 DLP は、パテント フィンガープリントを使用して、パテントを検出し、それらの電子メールをブロックします。 または、法的部門が他の組織に対して特許を送信できるようにする必要がある場合もあります。 DLP ポリシーでこれらの部門の例外を作成して、特定の部署が機密情報を送信できるようにしたり、ビジネス上の理由でポリシー ヒントをオーバーライドしたりすることもできます。

### <a name="supported-file-types"></a>サポートされているファイルの種類

ドキュメント フィンガープリントでは、メール フロー ルール (トランスポート ルールとも呼ばれます) でサポートされているのと同じファイルの種類がサポートされます。 サポートされているファイルの種類の一覧については、「 [メール フロー ルールのコンテンツ検査でサポートされているファイルの種類](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)」を参照してください。 ファイルの種類に関する 1 つの簡単なメモ: メール フロー ルールもドキュメント フィンガープリントも .dotx ファイルの種類をサポートしていません。これは、Word のテンプレート ファイルであるため、混乱する可能性があります。 このトピックやその他のドキュメント フィンガープリント トピックに "template" という単語が表示されると、テンプレート ファイルの種類ではなく、標準フォームとして確立したドキュメントを参照します。

#### <a name="limitations-of-document-fingerprinting"></a>ドキュメント フィンガープリンティングの制限

ドキュメント フィンガープリントでは、次の場合、機密情報は検出されません。

- パスワードで保護されたファイル
- イメージのみが含まれているファイル
- ドキュメント フィンガープリントの作成に使用されたオリジナルのフォームのテキストがすべて含まれていないドキュメント
- 10 MB を超えるファイル

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>PowerShell を使用して、ドキュメントフィンガープリントに基づいて分類ルール パッケージを作成する

現時点では、ドキュメント フィンガープリントは [、Security & Compliance PowerShell](/powershell/exchange/connect-to-scc-powershell) でのみ作成できます。

DLP では、分類ルール パッケージを使用して機密コンテンツを検出します。 ドキュメント フィンガープリントに基づいて分類規則パッケージを作成するには、 **New-DlpFingerprint** コマンドレットと **New-DlpSensitiveInformationType コマンドレットを** 使用します。 **New-DlpFingerprint** の結果はデータ分類規則の外部に格納されないため、常に同じ PowerShell セッションで **New-DlpFingerprint** と **New-DlpSensitiveInformationType** または **Set-DlpSensitiveInformationType** を実行します。 次の例では、C:\My Documents\Contoso Employee Template.docx ファイルに基づいて新しいドキュメント フィンガープリントを作成します。 同じ PowerShell セッションで **New-DlpSensitiveInformationType** コマンドレットを使用して新しい指紋を使用できるように、新しい指紋を変数として保存します。

```powershell
$Employee_Template = ([System.IO.File]::ReadAllBytes('C:\My Documents\Contoso Employee Template.docx'))
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

ここで、C:\My Documents\Contoso Customer Information Form.docx ファイルのドキュメント フィンガープリントを使用する、"Contoso Employee Confidential" という名前の新しいデータ分類ルールを作成してみましょう。

```powershell
$Customer_Form = ([System.IO.File]::ReadAllBytes('C:\My Documents\Contoso Customer Information Form.docx'))
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information."
```

**Get-DlpSensitiveInformationType** コマンドレットを使用して、すべての DLP データ分類ルール パッケージを検索できるようになりました。この例では、"Contoso Customer Confidential" はデータ分類ルール パッケージの一覧の一部です。

最後に、Microsoft Purview コンプライアンス ポータルの DLP ポリシーに "Contoso Customer Confidential" データ分類ルール パッケージを追加します。 この例では、"ConfidentialPolicy" という名前の既存の DLP ポリシーにルールを追加します。

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

次の例に示すように、Exchange Onlineのメール フロー ルールでデータ分類ルール パッケージを使用することもできます。 このコマンドを実行するには、まず [PowerShell に接続Exchange Online必要があります](/powershell/exchange/connect-to-exchange-online-powershell)。 また、ルール パッケージがMicrosoft Purview コンプライアンス ポータルから Exchange 管理センターに同期されるまでに時間がかかることにも注意してください。

```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

DLP で Contoso Customer Form.docxドキュメント フィンガープリントに一致するドキュメントが検出されるようになりました。

構文とパラメーターの情報については、次を参照してください。

- [New-DlpFingerprint](/powershell/module/exchange/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](/powershell/module/exchange/Get-DlpSensitiveInformationType)
