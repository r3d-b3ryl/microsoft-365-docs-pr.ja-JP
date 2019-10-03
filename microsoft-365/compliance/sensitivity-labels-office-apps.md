---
title: Office アプリにおける機密ラベルの機能
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密ラベルを使用すると、機密コンテンツの分類が可能になり、機密コンテンツの保護に役立ちます。このラベルを使用することで、共同作業の生産性や機能性が低下することはありません。機密ラベルは、ラベル付けされたコンテンツに暗号化や透かしなどの保護設定を強制適用するために使用できます。
ms.openlocfilehash: 1de7eadfcf95a54917c1d5e2cc0d42cc1ad486a5
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378655"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a>Office アプリにおける機密ラベルの機能

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a>Office アプリケーションで機密ラベルを使用するための前提条件について

### <a name="common-requirements"></a>一般的な要件 

- 統合された機密ラベルは[セキュリティ/コンプライアンス センターで構成、公開されている](https://aka.ms/managemip)必要があります。
- ユーザーは業務用アカウントを使って Office にログインする必要があります。
- ユーザーには Office 365 E3 以上のライセンスが割り当てられている必要があります。

### <a name="additional-requirements-for-office-for-windows"></a>Office for Windows のその他の要件 

- Azure Information Protection クライアントが Office で実行されていない必要があります。 「[機密ラベルは Office for Windows で Azure Information Protection クライアントと一緒に実行できますか?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)」も参照してください。

### <a name="additional-requirements-for-outlook-on-all-platforms"></a>すべてのプラットフォームの Outlook に関するその他の要件 

- ラベル構成で、コンテンツ マーキングを有効にした場合に、コンテンツ マーキングが転送中に挿入されるようにするには、Exchange Online を使用している必要があります。

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a>今日の Office でサポートされている機密ラベル機能について 

<table border="1" cellspacing="0" cellpadding="0">
<th><font size="-1">機能<th><font size="-1">Windows<th><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</tr>
<tr><td>

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook


<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook </b>
</tr>

<tr>
<td><font size="-1">ラベルを手動で適用、変更、または削除する<td><font size="-1"><b>はい</b><br><font size="-1">1910以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">16.21.0以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">2.21以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1"><b>はい</b><br><font size="-1">16.0.11231以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup><td><font size="-1">近日公開<sup>3</sup>

<tr>
<td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">既定のラベルを適用する</a>
<td><font size="-1"><b>はい</b><br><font size="-1">1910以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">16.21.0以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">2.21以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1"><b>はい</b><br><font size="-1">16.0.11231以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">ラベル変更の正当な理由を要求する</a><sup>1</sup>
<td><font size="-1"><b>はい</b><br><font size="-1">1910以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">16.21.0以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">2.21以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1"><b>はい</b><br><font size="-1">16.0.11231以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">カスタム ヘルプ ページへのリンクを提供する</a>
<td><font size="-1"><b>はい</b><br><font size="-1">1910以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">16.21.0以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">2.21以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1"><b>はい</b><br><font size="-1">16.0.11231以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">コンテンツをマークする</a>
<td><font size="-1"><b>はい</b><br><font size="-1">1910以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">16.21.0以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">2.21以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1"><b>はい</b><br><font size="-1">16.0.11231以上</font
><td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>

<tr><td><font size="-1">定義済みのアクセス許可を割り当てる
<td><font size="-1"><b>はい</b><br><font size="-1">1910以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">16.21.0以上</font>

<td><font size="-1"><b>はい</b><br><font size="-1">2.21以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1"><b>はい</b><br><font size="-1">16.0.11231以上</font>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">近日公開<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">ユーザーがアクセス許可を割り当てる</a>
<td><font size="-1"><b>はい</b><sup>2</sup><br><font size="-1">1910以上</font>

<td><font size="-1"><b>はい</b><sup>2</sup><br><font size="-1">16.21.0以上</font>

<td><font size="-1">TBD
<td><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">TBD<td
><font size="-1">近日公開<sup>3</sup>
<td><font size="-1">TBD
<td><font size="-1">近日公開<sup>3</sup>

<tr><td><font size="-1">管理者用に<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">ラベルの分析</a>を送信する
<td><font size="-1">TBD

<td><font size="-1">TBD

<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD

<tr><td><font size="-1">ユーザーがメールとドキュメントにラベルを適用することを必須にする
<td><font size="-1">TBD

<td><font size="-1">TBD

<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">機密ラベルをコンテンツに自動的に適用する</a>
<td><font size="-1">TBD

<td><font size="-1">TBD

<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
</table>

<br><sup>1</sup>構成されている場合、ユーザーはラベルのダウングレードを正当化するよう求められます。 ただし、このような根拠のあるデータは、管理者はまだ使用できません。 "管理者用にラベル分析データを送信する" 機能がサポートされている場合に使用できるようになります。
<br><sup>2</sup> "ユーザーにアクセス許可を割り当てられるようにする" は、現在 Outlook for Windows と Outlook for Mac でのみ使用できます。 Word、Excel、PowerPoint の可用性は TBD です。
<br><sup>3</sup> 2019年の暦年第 4 四半期に予定されています。

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a>コンテンツに機密ラベルが付与された後に、コンテンツ マークや暗号化が適用される時期

| アプリケーション | コンテンツのマーケティング | 暗号化
| --- | --- | --- |
| すべてのプラットフォームの Word、Excel、PowerPoint | 直ちに | 直ちに |
| Outlook for PC と Outlook for Mac | Exchange Online でメールが送信された後 | 直ちに |
| すべてのプラットフォームの Word、Excel、PowerPoint | Exchange Online でメールが送信された後 | Exchange Online でメールが送信された後 |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a>機密ラベルは Office for Windows で Azure Information Protection クライアントと一緒に実行できますか?

いいえ。 機密ラベルは、Azure Information Protection クライアントが Office for Windows で読み込まれた場合にオフになります。

Azure Information Protection クライアントがインストールされていても、代わりに機密ラベルを使用する場合は、次のことができます。

1.  **Office の [秘密度] 機能を使用して秘密ラベルを適用して表示する**のグループポリシー設定を構成します。この設定は、**ユーザーの構成/管理用テンプレート/Microsoft Office 2016/セキュリティ設定**にあります。

  >注: この設定は従来のグループ ポリシーの展開メカニズムか、[Office クラウド ポリシー サービス](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)から展開できます。 
 
  または、Azure Information Protection クライアントをアンインストール、または [無効](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d)にできます。 

2. すべての Office アプリケーションを再起動します。

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a>機密ラベルは、Office 2016 または Office 2019 のようなサブスクリプション以外 Office のバージョンでサポートされますか?

いいえ。 機密ラベルは Office 365 サブスクリプションでのみサポートされ、サブスクリプション以外のいずれのバージョンでもサポートされません。 ただし、Azure Information Protection の統合されたラベル クライアントは、サブスクリプション以外の Office のバージョンで使用できます。 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a>以前は、保護テンプレートを展開してから機密ラベルを設定しました。 どうなりましたか?

機密ラベルが有効になっていると、管理者が定義した[保護テンプレート](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)は Office のユーザー環境から非表示になります。暗号化が有効になっている機密ラベルでは冗長であるためです。 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a>ファイルまたはメールに複数の分類を含めることはできますか?

ユーザーは、ドキュメントまたはメールごとに一度に 1 つずつラベルを選ぶことができます。多くの場合、分類は 1 つになります。 ただし、ユーザーがサブラベルを選択すると、実際にプライマリ ラベルとセカンダリ ラベルの 2 つのラベルが同時に適用されます。 サブラベルを使用すると、ファイルには、追加の制御レベルに対して親子関係を表す 2 つの分類を含めることができます。 

たとえば、 **秘密** ラベルは **法務** や **財務**などのサブラベルが含まれる場合があります。 このサブラベルには、さまざまな分類の視覚的なマーキングと、多種多様な Rights Management テンプレートを適用できます。 ユーザーは **秘密** ラベルを単独では選択できません (たとえば、 **法務**などのサブラベルのうちの 1 つのみなど)。 結果として表示されるラベルは、 **秘密** / **法務**です。 ファイルのメタデータには、 **秘密**のカスタム テキスト プロパティ、 **法務**のカスタム テキスト プロパティ、両方の値 (**秘密ラベル**) を含む別のカスタム テキスト プロパティがあります。 

サブラベルを使用する場合は、プライマリ ラベルに視覚的なマーキング、保護、条件を構成しないでください。 サブレベルを使用する場合は、サブラベルでのみこれらの設定を構成します。 プライマリ ラベルとサブラベルでこれらの設定を構成すると、サブラベルの設定が優先されます。

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a>メールにラベルが付けられている場合は、添付ファイルに同じラベルを自動的に付けますか?

いいえ。 添付ファイルのあるメール メッセージにラベルを付けると、この添付ファイルのラベルは同じラベルを継承しません。 ラベルがない場合、または別々にラベルを適用していない場合、添付ファイルはそのまま残ります。 ただし、メールのラベルが保護されている場合、その保護は Office の添付ファイルに適用されます。

## <a name="additional-resources"></a>その他のリソース

[Azure Information Protection での分類とラベル付けについてよく寄せられる質問](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[Office 内のドキュメントとメールに機密ラベルを適用する](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)