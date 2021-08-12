---
title: ドキュメント フィンガープリンティング
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
localization_priority: Normal
description: 組織内のインフォメーション ワーカーは、日常的にさまざまな種類の機密情報を処理します。 ドキュメント フィンガープリンティングは、組織全体で使用される標準フォームを特定することによってこの情報の保護を容易にします。 このトピックでは、ドキュメント フィンガープリントの背後にある概念と、PowerShell を使用して作成する方法について説明します。
ms.openlocfilehash: e82d4947cac96550c9c720a6c55ec21dca4152ba45c7ce114eb3ba07a276a223
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53814224"
---
# <a name="document-fingerprinting"></a>ドキュメント フィンガープリンティング

組織内のインフォメーション ワーカーは、日常的にさまざまな種類の機密情報を処理します。 セキュリティ コンプライアンス センターでは、ドキュメント フィンガープリントを使用すると、組織全体で使用される標準フォームを識別することで、この情報を &amp; 簡単に保護できます。 このトピックでは、ドキュメント フィンガープリントの背後にある概念と、PowerShell を使用して作成する方法について説明します。
  
## <a name="basic-scenario-for-document-fingerprinting"></a>ドキュメント フィンガープリンティングに関する基本的なシナリオ

ドキュメントフィンガープリントは、標準フォームを機密情報の種類に変換するデータ損失防止 (DLP) 機能で、DLP ポリシーのルールで使用できます。 たとえば、空白の特許テンプレートに基づいてドキュメントフィンガープリントを作成し、機密コンテンツが入力されたすべての送信特許テンプレートを検出してブロックする DLP ポリシーを作成できます。 必要に応じて、ポリシー[](use-notifications-and-policy-tips.md)ヒントを設定して、送信者が機密情報を送信している可能性を通知し、送信者は受信者が特許を受け取る資格を持っている必要があります。 このプロセスは、組織内で使用されているテキスト ベースのフォームで動作します。 アップロードできるフォームのその他の例を次に示します。
  
- 政府機関フォーム
- Health Insurance Portability and Accountability Act (HIPAA) 準拠フォーム  
- 人事部門の従業員情報フォーム
- 組織用に特別に作成されたカスタム フォーム

組織で機密情報を送信するときに特定のフォームを使用するという業務習慣が既に確立されていることが理想的です。 ドキュメントフィンガープリントに変換する空のフォームをアップロードし、対応するポリシーを設定した後、DLP は、その指紋に一致する送信メール内のドキュメントを検出します。

## <a name="how-document-fingerprinting-works"></a>ドキュメント フィンガープリンティングのしくみ

ドキュメントに実際の指紋があるわけではありませんが、名前からその機能を想像することができます。 人間の指紋に固有のパターンがあるように、ドキュメントにも固有の単語パターンがあります。 ファイルをアップロードすると、DLP はドキュメント内の一意の単語パターンを識別し、そのパターンに基づいてドキュメント フィンガープリントを作成し、そのドキュメント フィンガープリントを使用して同じパターンを含む送信ドキュメントを検出します。 これにより、フォームまたはテンプレートをアップロードすると、ドキュメント フィンガープリントの最も有効なタイプが作成されます。 フォームに記入するユーザーは全員同じオリジナルの単語セットを使用し、その上で独自の単語をドキュメントに追加します。 送信ドキュメントがパスワードで保護されていない限り、元のフォームのすべてのテキストが含まれている限り、DLP はドキュメントがドキュメントの指紋と一致するかどうかを判断できます。

> [!IMPORTANT]
> 今のところ、DLP はドキュメント フィンガープリントをオンラインでのみ検出Exchangeできます。

次の例では、特許情報テンプレートに基づいてドキュメント フィンガープリントを作成した場合に何が行われるかを示しています。ただし、ドキュメント フィンガープリントは、任意のフォームに基づいて作成できます。
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>特許情報テンプレートのドキュメント フィンガープリントと一致する特許情報ドキュメントの例

![ドキュメントフィンガープリントの図。](../media/Document-Fingerprinting-diagram.png)
  
特許テンプレートには、これらの各フィールドの空白フィールド "Patent title"、"Inventors"、および "Description" と説明が含まれています。これは単語パターンです。 元の特許テンプレートをアップロードすると、サポートされているファイルの種類の 1 つで、テキスト形式で保存されます。 DLP は、この単語パターンをドキュメント フィンガープリントに変換します。これは、元のテキストを表す一意のハッシュ値を含む小さな Unicode XML ファイルであり、指紋は Active Directory のデータ分類として保存されます。 (セキュリティ対策として、元のドキュメント自体はサービスに保存されません。ハッシュ値だけが格納され、元のドキュメントをハッシュ値から再構築できません)。その後、特許指紋は機密情報の種類になり、DLP ポリシーに関連付けできます。 指紋を DLP ポリシーに関連付けると、DLP は、特許指紋に一致するドキュメントを含む送信メールを検出し、組織のポリシーに従って処理します。 

たとえば、通常の従業員が特許を含む送信メッセージを送信するのを防ぐ DLP ポリシーを設定できます。 DLP は、特許指紋を使用して特許を検出し、それらの電子メールをブロックします。 あるいは、ビジネス上の必要がある場合に、法務部門が他の組織に特許を送信できる場合があります。 特定の部署に機密情報の送信を許可するには、DLP ポリシーでそれらの部門の例外を作成するか、ビジネス上の正当性を持つポリシー ヒントを上書きできます。
  
### <a name="supported-file-types"></a>サポートされているファイルの種類

ドキュメント フィンガープリントは、メール フロー ルール (トランスポート ルールとも呼ばれる) でサポートされているのと同じ種類のファイルをサポートします。 サポートされているファイルの種類の一覧については、「メール フロー ルールのコンテンツ 検査でサポートされるファイル [の種類」を参照してください](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。 ファイルの種類に関する 1 つの簡単なメモ: メール フロー ルールもドキュメント フィンガープリントも .dotx ファイルの種類をサポートしないので、Word のテンプレート ファイルなので混乱する可能性があります。 このトピックおよび他のドキュメント フィンガープリント のトピックに"template" という単語が表示される場合は、テンプレート ファイルの種類ではなく、標準フォームとして確立したドキュメントを参照します。
  
#### <a name="limitations-of-document-fingerprinting"></a>ドキュメント フィンガープリンティングの制限

ドキュメントフィンガープリントは、次の場合に機密情報を検出しません。
  
- パスワードで保護されたファイル
- イメージのみが含まれているファイル
- ドキュメント フィンガープリントの作成に使用されたオリジナルのフォームのテキストがすべて含まれていないドキュメント
- 10 MB を超えるファイル

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>PowerShell を使用して、ドキュメントフィンガープリントに基づいて分類ルール パッケージを作成する

現時点では、セキュリティ コンプライアンス センターで PowerShell を使用してドキュメント フィンガープリントのみを &amp; 作成できます。 接続するには、「コンプライアンス[センター powerShell Connectセキュリティ &にアクセスする」を参照してください](/powershell/exchange/connect-to-scc-powershell)。

DLP は分類ルール パッケージを使用して機密コンテンツを検出します。 ドキュメント フィンガープリントに基づいて分類ルール パッケージを作成するには **、New-DlpFingerprint** コマンドレットと **New-DlpSensitiveInformationType** コマンドレットを使用します。 **New-DlpFingerprint** の結果はデータ分類ルールの外側に格納されないので、同じ PowerShell セッションで常に **New-DlpFingerprint** と **New-DlpSensitiveInformationType** または **Set-DlpSensitiveInformationType** を実行します。 次の例では、C:\My Documents\Contoso Employee Template.docx ファイルに基づいて新しいドキュメント フィンガープリントを作成します。 同じ PowerShell セッションで **New-DlpSensitiveInformationType** コマンドレットを使用して新しい指紋を使用できるように、新しい指紋を変数として保存します。
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

ここで、C:\My Documents\Contoso Customer Information Form.docx ファイルのドキュメント フィンガープリントを使用する、"Contoso Employee Confidential" という名前の新しいデータ分類ルールを作成してみましょう。
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

**Get-DlpSensitiveInformationType** コマンドレットを使用してすべての DLP データ分類ルール パッケージを検索できます。この例では、"Contoso Customer Confidential" はデータ分類ルール パッケージの一覧の一部です。 
  
最後に、セキュリティ コンプライアンス センターの DLP ポリシーに"Contoso Customer Confidential" データ分類ルール パッケージを &amp; 追加します。 この例では、"ConfidentialPolicy" という名前の既存の DLP ポリシーにルールを追加します。

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

また、次の例に示すように、Exchange Online のメール フロー ルールでデータ分類ルール パッケージを使用することもできます。 このコマンドを実行するには、まず[PowerShell をConnect Exchange Online必要があります](/powershell/exchange/connect-to-exchange-online-powershell)。 また、ルール パッケージがセキュリティ コンプライアンス センターから管理センターに同期するのに時間 &amp; Exchange注意してください。
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

DLP では、Contoso Customer と一致するドキュメントが検出され、Form.docx指紋が検出されます。
  
構文とパラメーターの情報については、以下を参照してください。

- [New-DlpFingerprint](/powershell/module/exchange/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](/powershell/module/exchange/Get-DlpSensitiveInformationType)
