---
title: オンボーディングの問題とエラー メッセージのトラブルシューティング
description: Microsoft Defender for Endpoint のセットアップを完了する際にオンボーディングの問題とエラー メッセージのトラブルシューティングを行います。
keywords: トラブルシューティング、トラブルシューティング、Azure Active Directory、オンボーディング、エラー メッセージ、エラー メッセージ、エンドポイント用 microsoft Defender
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

このページでは、Microsoft Defender for Endpoint サービスのセットアップ時に発生する可能性がある問題をトラブルシューティングするための詳細な手順について説明します。

エラー メッセージが表示された場合、Microsoft 365 Defender問題と関連するリンクが提供される内容に関する詳細な説明が表示されます。

## <a name="no-subscriptions-found"></a>サブスクリプションが見つかりません

Microsoft 365 Defender にアクセス中にサブスクリプションが見つからないというメッセージが表示される場合は、ユーザーのポータルへのログインに使用される Azure Active Directory (Azure AD) には、Microsoft Defender for Endpoint ライセンスが存在しないという意味です。

潜在的な理由:

- Windows E5 ライセンスと Office E5 ライセンスは、別のライセンスです。
- ライセンスは購入されましたが、このインスタンスにプロビジョニングAzure ADされません。
  - ライセンス プロビジョニングの問題である可能性があります。
  - サービスへの認証に使用されるライセンスとは異なるMicrosoft Azure ADにライセンスをプロビジョニングした可能性があります。

どちらの場合も、Microsoft Defender for [Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) または Volume ライセンス のサポートで Microsoft サポートに問い [合わせるべきです](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)。

:::image type="content" source="images/atp-no-subscriptions-found.png" alt-text="[サブスクリプションが見つかりません] ページ" lightbox="images/atp-no-subscriptions-found.png":::

## <a name="your-subscription-has-expired"></a>サブスクリプションの有効期限が切れています

サブスクリプションへのアクセス中Microsoft 365 Defenderサブスクリプションの有効期限が切れたメッセージが表示される場合、オンライン サービス サブスクリプションの有効期限が切れています。 Microsoft Defender for Endpoint サブスクリプションは、他のオンライン サービス サブスクリプションと同様に有効期限があります。

ライセンスの更新または延長は、任意の時点で選択できます。 有効期限が切れた後にポータルにアクセスすると、サブスクリプションの有効期限が切れたメッセージが表示され、ライセンスを更新しない場合は、デバイスのオフボード パッケージをダウンロードするオプションが表示されます。

> [!NOTE]
> セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

:::image type="content" source="images/atp-subscription-expired.png" alt-text="サブスクリプションの有効期限が切れた通知メッセージ" lightbox="images/atp-subscription-expired.png":::

## <a name="you-are-not-authorized-to-access-the-portal"></a>ポータルへのアクセスが承認されていない

ポータルへのアクセスが承認されていない場合、Microsoft Defender for Endpoint はセキュリティ監視、インシデント調査、応答製品であり、アクセスはユーザーによって制限および制御されます。
詳細については、「ユーザー アクセスをポータルに [**割り当てる」を参照してください**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)。

:::image type="content" source="images/atp-not-authorized-to-access-portal.png" alt-text="アクセスが禁止された通知メッセージ" lightbox="images/atp-not-authorized-to-access-portal.png":::

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a>現在、ポータルの一部のセクションでデータを使用できない

ポータル ダッシュボードや他のセクションに「現在データが使用できない」などのエラー メッセージが表示される場合は、次の手順を実行します。

:::image type="content" source="images/atp-data-not-available.png" alt-text="データの利用不能通知メッセージ" lightbox="images/atp-data-not-available.png":::

Web ブラウザーで、その下のすべての `security.windows.com` サブドメインを許可する必要があります。 たとえば、「 `*.security.windows.com` 」のように入力します。

## <a name="portal-communication-issues"></a>ポータル通信の問題

ポータルへのアクセス、不足しているデータ、またはポータルの一部へのアクセス制限に関する問題が発生した場合は、次の URL が許可され、通信のために開いているか確認する必要があります。

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
