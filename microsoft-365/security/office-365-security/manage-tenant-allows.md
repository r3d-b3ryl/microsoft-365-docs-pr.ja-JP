---
title: テナント許可/ブロック一覧で許可を管理する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150manage-tenant-allows.md
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナント許可/ブロック一覧で許可を構成する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3823290e9f239b14e4bf97fe1ae8ef7020561697
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314113"
---
# <a name="add-allows-in-the-tenant-allowblock-list"></a>テナントの許可/禁止リストの許可リストを追加する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

管理者は、テナント許可/ブロック一覧に直接許可を追加できません。 代わりに、管理者申請プロセスを使用して、対応する URL、ファイル、送信者がテナント許可/ブロック一覧に追加されるので、ブロックされたメッセージを送信します。 ファイル、URL、または送信者のブロックが発生していない場合、許可は作成されません。 メッセージが誤ってブロックされた誤検知と判断されたほとんどの場合、許可は、システムに自然に許可する時間を与えるために必要な限り保持されます。

> [!IMPORTANT]
> Microsoft は許可を管理しますので、送信者、URL、またはファイルを使用すると、不要または悪いと見なされる許可は削除されます。 これは、環境を保護し、許可の構成ミスを防ぐためです。 同意が得ない場合は、メッセージが引き続き不良と見なされる理由を判断するためにサポート ケースが必要になる場合があります。

## <a name="add-sender-allows-using-the-submissions-portal"></a>送信ポータルを使用して送信者を追加できます 

[送信] ページの [送信者 (またはドメイン) を許可Microsoft 365 Defender。 

1. [送信Microsoft 365 Defender] <https://security.microsoft.com>の [アクション **] &** \> **に移動します**。 または、[申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission>。

2. [申請 **] ページで**、[メール]  ![タブが選択されているのを確認し、[分析用に Microsoft に送信] アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に提出します**。

3. ネットワーク メッセージ **ID を追加するか** 、電子メール ファイルをアップロードしてメッセージを送信するには、Microsoft に送信して確認フライアウトを使用します。 

4. [Microsoft **に提出する理由を** 選択する] セクションで、[ブロックされていない (誤検知) **必要があります] を選択します**。 

5. [このオプション **のようなメッセージを許可する] をオン** にします。 

6. [削除 **後に削除** ] ドロップダウン リストから、許可オプションを有効にする期間を指定します。

7. 完了したら、[送信] ボタン **をクリック** します。

> [!div class="mx-imgBorder"]
> ![分析の例については、Microsoft にマルウェアを送信します。](../../media/admin-submission-allow-messages.png)

## <a name="add-url-allows-using-the-submissions-portal"></a>申請ポータルを使用して URL を追加できます

[送信] ページの **[URL を許可** Microsoft 365 Defender。

1. [送信Microsoft 365 Defender] <https://security.microsoft.com>の [アクション **] &** \> **に移動します**。 または、[申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission>。

2. [申請 **] ページで** [URL] タブ **を選択** し、[分析用 ![に Microsoft に送信] アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に提出します**。

3. URL を **追加してメッセージを送信するには、確認** 用に Microsoft に送信するフライアウトを使用します。

4. [Microsoft **に提出する理由を** 選択する] セクションで、[ブロックされていない (誤検知) **必要があります] を選択します**。

5. [次のような **URL を許可する] オプションをオン** にします。

6. [削除 **後に削除** ] ドロップダウン リストから、許可オプションを有効にする期間を指定します。

7. 完了したら、[送信] ボタン **をクリック** します。

> [!div class="mx-imgBorder"]
> ![分析用の URL を送信します。](../../media/submit-url-for-analysis.png)

## <a name="add-file-allows-using-the-submissions-portal"></a>ファイルの追加では、申請ポータルを使用できます

[送信] ページ **の [ファイルを許可** する] Microsoft 365 Defender。

[送信Microsoft 365 Defender] <https://security.microsoft.com>の [アクション **] &** \> **に移動します**。 または、[申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission>。

2. [申請 **] ページで** 、[電子メールの添付ファイル] タブ **を選択し** 、[分析用 ![に Microsoft に送信] アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に提出します**。

3. ファイルまたは **ファイルを追加してメッセージ** を送信するには、Microsoft に送信してレビュー フライアウトを使用します。

4. [Microsoft **に提出する理由を** 選択する] セクションで、[ブロックされていない (誤検知) **必要があります] を選択します**。

5. [次のようなファイル **を許可する] オプションをオン** にします。

6. [削除 **後に削除** ] ドロップダウン リストから、許可オプションを有効にする期間を指定します。

7. 完了したら、[送信] ボタン **をクリック** します。

> [!div class="mx-imgBorder"]
> ![分析用に電子メールを送信します。](../../media/submit-email-for-analysis.png)


## <a name="create-spoofed-sender-allow-entries-using-microsoft-365-defender"></a>スプーフィングされた送信者許可エントリを作成するには、Microsoft 365 Defender

> [!NOTE]
> 
> - スプー _フィング_ されたユーザーと、ドメイン ペアで定義されている送信インフラストラクチャの組み合わせだけが、スプーフィングを許可またはブロックされます。
> - ドメイン ペアの許可エントリまたはブロック エントリを構成すると、そのドメイン ペアからのメッセージはスプーフィング インテリジェンスインサイトに表示されなくなりました。
> - スプーフィングされた送信者のエントリは有効期限が切れることはありません。
> - スプーフィングは、許可とブロックの両方をサポートします。 URL は許可のみをサポートします。

1. [ルール] Microsoft 365 Defender  \>  \>  \> <https://security.microsoft.com>で、[ルール] セクション&[脅威ポリシー&テナント許可 **/** ブロックリスト] の [メール] グループの [ポリシー] に **移動** します。 または、[テナントの許可/ブロックリスト] **ページに** 直接移動するには、 を使用します <https://security.microsoft.com/tenantAllowBlockList>。

2. [テナントの **許可/ブロック一覧] ページ** で、[スプーフィング] タブ **を選択** し、[追加] アイコンを ![クリックします。](../../media/m365-cc-sc-create-icon.png) **[追加]** 。

3. 表示される **[新しいドメイン ペアの追加** ] フライアウトで、次の設定を構成します。
   - **ワイルドカードを使用して新しいドメイン ペア** を追加する: 1 行に 1 つのドメイン ペアを入力し、最大 20 を入力します。 スプーフィングされた送信者エントリの構文の詳細については、「 [Manage the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。
   - **スプーフィング** の種類: 次のいずれかの値を選択します。
     - **内部**: スプーフィングされた送信者は、組織 (受け入れドメイン) に属する [ドメイン内にいます](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
     - **外部**: スプーフィングされた送信者が外部ドメイン内にある。
   - **アクション**: [許可] **または [ブロック]** を **選択します**。

4. 完了したら、**[追加]** をクリックします。

## <a name="add-spoofed-sender-allow-entries-using-powershell"></a>PowerShell を使用してスプーフィングされた送信者許可エントリを追加する

PowerShell のテナント許可/ブロック一覧にスプーフィング[された送信者Exchange Onlineするには](/exchange/connect-to-exchange-online-powershell)、次の構文を使用します。

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。

## <a name="related-articles"></a>関連記事

- [管理者による報告](admin-submission.md)
- [誤検知と誤検知を報告する](report-false-positives-and-false-negatives.md)
