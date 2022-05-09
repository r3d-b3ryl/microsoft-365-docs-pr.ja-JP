---
title: オンボードの問題とエラー メッセージのトラブルシューティング
description: Microsoft Defender for Endpointのセットアップ中にオンボードの問題とエラー メッセージのトラブルシューティングを行います。
keywords: トラブルシューティング, トラブルシューティング, Azure Active Directory, オンボード, エラー メッセージ, エラー メッセージ, Microsoft Defender for endpoint
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: cfbd91743ed2e61809d9e2b6f0243b5c327bdae4
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467557"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a>サブスクリプションとポータル アクセスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

このページでは、Microsoft Defender for Endpoint サービスのセットアップ時に発生する可能性がある問題をトラブルシューティングする詳細な手順について説明します。

エラー メッセージが表示された場合、Microsoft 365 Defenderは問題の内容と関連リンクが提供される詳細な説明を提供します。

## <a name="no-subscriptions-found"></a>サブスクリプションが見つかりません

サブスクリプション **が見つからない** というメッセージが表示Microsoft 365 Defenderアクセス中に、ユーザーをポータルにログインするために使用されるAzure Active Directory (Azure AD) にMicrosoft Defender for Endpointライセンスがないことを意味します。

考えられる理由:

- Windows E5 ライセンスと Office E5 ライセンスは、別のライセンスです。
- ライセンスは購入されましたが、このAzure AD インスタンスにプロビジョニングされていません。
  - ライセンス プロビジョニングの問題である可能性があります。
  - サービスへの認証に使用されるMicrosoft Azure ADとは異なるMicrosoft Azure ADにライセンスを誤ってプロビジョニングした可能性があります。

どちらの場合も、[一般Microsoft Defender for Endpoint サポート](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913)または[ボリューム ライセンス サポート](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)の Microsoft サポートにお問い合わせください。

:::image type="content" source="images/atp-no-subscriptions-found.png" alt-text="[サブスクリプションが見つかりません] ページ" lightbox="images/atp-no-subscriptions-found.png":::

## <a name="your-subscription-has-expired"></a>サブスクリプションの有効期限が切れています

**サブスクリプションの有効期限が切れた** Microsoft 365 Defenderアクセス中にメッセージが表示された場合は、オンライン サービス サブスクリプションの有効期限が切れています。 Microsoft Defender for Endpointサブスクリプションには、他のオンライン サービス サブスクリプションと同様に、有効期限があります。

ライセンスの更新または延長はいつでも選択できます。 有効期限後にポータルにアクセスすると、 **サブスクリプションの有効期限が切れた** というメッセージが表示され、デバイスオフボード パッケージをダウンロードするオプションが表示されます。ライセンスを更新しないことを選択した場合。

> [!NOTE]
> セキュリティ上の理由から、オフボード デバイスに使用されるパッケージは、ダウンロード日の 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

:::image type="content" source="images/atp-subscription-expired.png" alt-text="サブスクリプションの有効期限が切れた通知メッセージ" lightbox="images/atp-subscription-expired.png":::

## <a name="you-are-not-authorized-to-access-the-portal"></a>ポータルにアクセスする権限がありません

**ポータルへのアクセスを許可されていないユーザーを** 受け取った場合は、Microsoft Defender for Endpointがセキュリティ監視、インシデント調査、対応製品であるため、アクセスが制限され、ユーザーによって制御されていることに注意してください。
詳細については、「 [**ポータルへのユーザー アクセスの割り当て」を**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)参照してください。

:::image type="content" source="images/atp-not-authorized-to-access-portal.png" alt-text="アクセスが許可されていない通知メッセージ" lightbox="images/atp-not-authorized-to-access-portal.png":::

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a>現在、ポータルの一部のセクションではデータを使用できません

ポータル ダッシュボードとその他のセクションに、"現在使用できないデータ" などのエラー メッセージが表示される場合:

:::image type="content" source="images/atp-data-not-available.png" alt-text="データの利用不可通知メッセージ" lightbox="images/atp-data-not-available.png":::

Web ブラウザーで、その下にあるすべてのサブドメインを許可 `security.windows.com` する必要があります。 たとえば、「 `*.security.windows.com` 」のように入力します。

## <a name="portal-communication-issues"></a>ポータル通信の問題

ポータルへのアクセス、データの不足、またはポータルの一部へのアクセスの制限に関する問題が発生した場合は、次の URL が許可され、通信用に開かれていることを確認する必要があります。

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.security.microsoft.com`
- `https://automatediracs-eus-prd.security.microsoft.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com`
- `https://security.microsoft.com`
- `https://static2.sharepointonline.com`
