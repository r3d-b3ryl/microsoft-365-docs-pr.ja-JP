---
title: テナント許可/ブロック リストを使用してファイルを許可またはブロックする
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
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナント許可/ブロックリストでファイルを許可またはブロックする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65f5a0706b49312ee4b12a626f7ecd0d600c93df
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159905"
---
# <a name="allow-or-block-files-using-the-tenant-allowblock-list"></a>テナント許可/ブロック リストを使用してファイルを許可またはブロックする

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender ポータルまたは PowerShell を使用して、テナント許可/ブロック リスト内のファイルを許可またはブロックできます。

## <a name="create-block-file-entries"></a>ブロック ファイル エントリを作成する 

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defenderを使用する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **ファイル** ] タブを選択し、[ブロック] アイコンをクリック ![します。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

3. 表示される **[ブロック ファイル** ] ポップアップで、次の設定を構成します。
   - **ファイル ハッシュを追加** する: 行ごとに 1 つの SHA256 ハッシュ値を入力し、最大 20 個まで入力します。
   - **期限切れになることはありません**: 次のいずれかの手順を実行します。
     - 設定がオフになっていることを確認します (![オフに](../../media/scc-toggle-off.png)切り替えます)。[ **削除オン** ] ボックスを使用して、エントリの有効期限を指定します。

     または

     - 切り替えを右に移動して、期限切れにならないようにエントリを構成します。 ![オンに切り替えます。](../../media/scc-toggle-on.png).
   - **省略可能な注**: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらのファイルを含む電子メールは _、マルウェア_ としてブロックされます。

### <a name="use-powershell"></a>PowerShell を使う

テナント許可/ブロック リストにブロック ファイル エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType <FileHash> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

次の使用例は、有効期限が切れない指定されたファイルのブロック ファイル エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。

## <a name="create-allow-file-entries"></a>許可ファイル エントリを作成する

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defenderを使用する

Microsoft 365 Defenderの **[提出]** ページでファイルを許可します。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**Actions & submissions**\>] に移動 **します**。 または、[ **申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **送信] ページで** 、[ **電子メールの添付ファイル** ] タブを選択し、[分析のために Microsoft に送信] アイコンをクリック ![します。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

3. **[レビュー用に Microsoft に送信]** ポップアップを使用して、ファイルまたはファイルを追加してメッセージを送信します。

4. [ **Microsoft に送信する理由を選択** する] セクションで、[ **ブロックされていない必要があります (誤検知)]** を選択します。

5. **[次のようなファイルを許可する]** オプションをオンにします。

6. **[以下の後に削除]** ドロップダウン リストで、許可オプションを機能させる期間を選択します。

7. 完了したら、[ **送信]** ボタンをクリックします。

  :::image type="content" source="../../media/submit-email-for-analysis.png" alt-text="分析のために電子メールを送信します。" lightbox="../../media/submit-email-for-analysis.png":::

> [!NOTE]
>
> ファイルが再び検出されると、ファイルは起爆または評判チェックのために送信されず、他のすべてのファイル ベースのフィルターはスキップされます。 メール フロー中に、残りのフィルターでクリーンなファイルを含むメールが見つかると、電子メールが配信されます。

## <a name="view-file-entries"></a>ファイル エントリを表示する 

テナント許可/ブロック リストでブロック ファイル エントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

この例では、指定したファイル ハッシュ値の情報を返します。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。

## <a name="modify-file-entries"></a>ファイル エントリを変更する

テナント許可/ブロック リストの許可ファイル エントリまたはブロック ファイル エントリを変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。

## <a name="remove-file-entries"></a>ファイル エントリを削除する 

テナント許可/ブロック リストから許可ファイル エントリまたはブロック ファイル エントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash> -Ids <"Id1","Id2",..."IdN">
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。

## <a name="related-articles"></a>関連記事

- [管理者による報告](admin-submission.md)
- [誤検知と偽陰性を報告する](report-false-positives-and-false-negatives.md)
- [テナント許可/ブロック一覧で許可とブロックを管理する](manage-tenant-allow-block-list.md)
- [テナントの許可/ブロック一覧で電子メールを許可またはブロックする](allow-block-email-spoof.md)
- [テナント許可/ブロック リストの URL を許可またはブロックする](allow-block-urls.md)