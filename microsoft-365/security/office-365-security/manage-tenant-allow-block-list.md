---
title: テナント許可/ブロック一覧の許可とブロックを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
ms.date: 08/11/2022
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: セキュリティ ポータルのテナント許可/ブロック一覧で、許可とブロックを管理する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9993241a42b40fd670e83d0e28938fa9a4625086
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441595"
---
# <a name="manage-your-allows-and-blocks-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧で許可とブロックを管理する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含む Microsoft 365 組織では、Exchange Onlineメールボックスがない場合は、EOP フィルターの判定に同意しない可能性があります。 たとえば、適切なメッセージが無効 (誤検知) としてマークされたり、不適切なメッセージが許可されたり (偽陰性) されたりすることがあります。

Microsoft 365 Defender ポータルのテナント許可/ブロックリストを使用すると、Microsoft 365 フィルターの判定を手動でオーバーライドできます。 テナント許可/ブロック リストは、受信メッセージフォームの外部送信者 (組織内メッセージには適用されません) とユーザーのクリック時にメール フロー中に使用されます。

テナントの許可/ブロックの一覧は、Microsoft 365 Defender ポータルの <https://security.microsoft.com> \> **[ポリシー] &ルール**\>の [ルール] セクションの **[脅威ポリシー** \> **テナント許可/ブロック リスト****]** で使用できます。 **[テナント許可/ブロック リスト**] ページに直接移動するには、次を使用<https://security.microsoft.com/tenantAllowBlockList>します。

エントリの作成と構成の手順については、次のトピックを参照してください。

- **ドメインと電子メール アドレス** と **スプーフィングされた送信者**: [テナント許可/ブロック リストを使用して電子メールを許可またはブロックする](allow-block-email-spoof.md)
- **ファイル**: [テナント許可/ブロック リストを使用してファイルを許可またはブロックする](allow-block-files.md)
- **URL**: [テナント許可/ブロック リストを使用して URL を許可またはブロックします](allow-block-urls.md)。

これらの記事には、Microsoft 365 Defender ポータルと PowerShell の手順が含まれています。

## <a name="block-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リスト内のエントリをブロックする

提出ポータル ( *管理者申請* とも呼ばれます) <https://security.microsoft.com/reportsubmission> を使用して、次の種類のアイテムのブロック エントリを作成し、Microsoft に誤検知として報告します。

- **ドメインと電子メール アドレス**:
  - これらの送信者からのEmailメッセージは *、高信頼スパム* (SCL = 9) としてマークされます。 メッセージに対する処理は、受信者のメッセージを検出した [スパム対策ポリシー](configure-your-spam-filter-policies.md) によって決まります。 既定のスパム対策ポリシーと新しいカスタム ポリシーでは、信頼度の高いスパムとしてマークされたメッセージが既定で迷惑メール Email フォルダーに配信されます。 Standard および Strict [の事前設定済みセキュリティ ポリシー](preset-security-policies.md)では、信頼度の高いスパム メッセージが検疫されます。
  - 組織内のユーザーは、これらのブロックされたドメインとアドレスに電子メールを送信できません。 次の配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) を受け取ります。 `5.7.1  Your message can't be delivered because one or more recipients are blocked by your organization's tenant allow/block list policy.`

- **ファイル**: これらのブロックされたファイルを含むEmailメッセージは *、マルウェア* としてブロックされます。

- **URL**: これらのブロックされた URL を含むEmail メッセージは、*信頼度の高いフィッシングとして* ブロックされます。

テナント許可/ブロック リストでは、次の種類のアイテムのブロック エントリを直接作成することもできます。

- **ドメインと電子メール アドレス**、 **ファイル**、 **URL**。

- **スプーフィングされた送信者**: 既存の許可判定を [スプーフィング インテリジェンス](learn-about-spoof-intelligence.md)から手動でオーバーライドした場合、ブロックされたスプーフィングされた送信者は、テナント許可/ブロックリストの **[スプーフィングされた送信者** ] タブにのみ表示される手動ブロック エントリになります。

既定では、 **ドメインと電子メール アドレス**、 **ファイル** 、 **URL の** エントリは 30 日後にブロックされますが、90 日間の有効期限が切れるか、期限切れにならないように設定できます。 **スプーフィングされた送信者** のエントリをブロックすると、有効期限が切れることはありません。

## <a name="allow-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック 一覧のエントリを許可する

ほとんどの場合、テナント許可/ブロックリストに許可エントリを直接作成することはできません。

- **ドメインと電子メール アドレス**、 **ファイル**、 **URL**: テナント許可/ブロック リストに許可エントリを直接作成することはできません。 代わりに、送信ポータル <https://security.microsoft.com/reportsubmission> を使用して、 **電子メール**、 **電子メールの添付ファイル**、または **URL を** Microsoft に報告します **。これは、ブロックされていない必要があります (False positive)**。

- **スプーフィングされた送信者**:
  - スプーフィング インテリジェンスによってメッセージがスプーフィングとして既にブロックされている場合は、送信ポータルを <https://security.microsoft.com/reportsubmission> 使用して、電子 **メール** を Microsoft に報告します **。これはブロックされていない必要があります (False positive)**。
  - スプーフィング インテリジェンスがスプーフィングとしてメッセージを識別してブロックする前に、スプーフィングされた送信者の許可エントリをテナント許可/ブロック リストの [[スプーフィング](learn-about-spoof-intelligence.md)**された送信者**] タブでプロアクティブに作成できます。

次の一覧では、申請ポータルで誤検知として Microsoft に何かを報告した場合のテナント許可/ブロック リストでの動作について説明します。

- **Email添付ファイル** と **URL**: 許可エントリが作成され、テナント許可/ブロックリストの **[ファイル** または **URL**] タブに表示されます。

- **Email**: メッセージが Microsoft 365 フィルター スタックによってブロックされた場合、テナント許可/ブロックリストに許可エントリが作成される可能性があります。

  - メッセージが [スプーフィング インテリジェンス](learn-about-spoof-intelligence.md)によってブロックされた場合、送信者の許可エントリが作成され、テナント許可ブロックリストの **[スプーフィングされた送信者** ] タブに表示されます。

  - Defender for Office 365の[ドメインまたはユーザー偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)によってメッセージがブロックされた場合、許可エントリはテナント許可/ブロックリストに作成されません。 代わりに、メッセージを検出した [フィッシング対策ポリシー](configure-mdo-anti-phishing-policies.md#use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies)の **[信頼された送信者とドメイン] セクション** にドメインまたは送信者が追加されます。

  - メッセージが他の理由でブロックされた場合は、送信者の許可エントリが作成され、テナント許可ブロックリストの **[ドメイン&アドレス** ] タブに表示されます。

  - メッセージがブロックされておらず、送信者のエントリを許可する場合は作成されないため、[ **スプーフィングされた送信者** ] タブまたは [ **ドメイン & アドレス** ] タブには表示されません。

既定では、 **ドメインと電子メール アドレス**、 **ファイル** 、 **URL のエントリが** 30 日後に期限切れになるのを許可します。これは最大でもあります。 **スプーフィングされた送信者** のエントリが期限切れにならないようにします。

> [!NOTE]
> Microsoft が許可エントリを管理するため、不要な許可エントリは **ドメインと電子メール アドレス**、 **URL**、または **ファイル** が削除されます。 この動作により、組織が保護され、構成の誤った許可エントリを防ぐことができます。 判定に同意しない場合は、メッセージが依然として不適切と見なされる理由を判断するためにサポート ケースを開く必要がある場合があります。
>
> 許可は、メッセージが悪意のあると判断したフィルターに基づいて、メール フロー中に追加されます。 たとえば、送信者とメッセージ内の URL が正しくないと判断された場合、送信者の許可エントリが作成され、URL に対して許可エントリが作成されます。
>
> そのエンティティ (ドメインまたは電子メール アドレス、URL、ファイル) が再び検出されると、そのエンティティに関連付けられているすべてのフィルターがスキップされます。
>
> メール フロー中に、ドメインまたは電子メール アドレスからのメッセージがフィルター処理スタック内の他のチェックに合格した場合、メッセージは配信されます。 たとえば、 [電子メール認証](email-validation-and-authentication.md) に合格した場合、許可エントリの送信者からのメッセージが配信されます。

## <a name="what-to-expect-after-you-add-an-allow-or-block-entry"></a>許可エントリまたはブロック エントリを追加した後に必要なもの

申請ポータルまたはテナント許可/ブロック リストのブロック エントリを使用して許可エントリを追加した後、エントリはすぐに動作を開始する必要があります。

システムが許可またはブロックについて学習したかどうかを確認するために、エントリの有効期限を 30 日後に自動的に設定することをお勧めします。 そうでない場合は、システムに学習にさらに 30 日間を与えるために、別のエントリを作成する必要があります。
