---
title: 問題とエラー メッセージのトラブルシューティングと解決を行Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouse、エラー メッセージと問題のトラブルシューティングと解決に関するヘルプを参照してください。
ms.openlocfilehash: 957177dd20817f9b3d5fbc378f22b19eeaef1f7f
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403679"
---
# <a name="troubleshoot-and-resolve-problems-and-error-messages-in-microsoft-365-lighthouse"></a>問題とエラー メッセージのトラブルシューティングと解決を行Microsoft 365 Lighthouse

この記事では、エラー メッセージとエラー メッセージの使用中に発生する可能性のある問題について説明し、Microsoft 365 Lighthouse解決するためのトラブルシューティング手順を説明します。

## <a name="partner-onboarding"></a>パートナーオンボーディング

### <a name="message-when-trying-to-access-lighthouse-microsoft-365-lighthouse-doesnt-support-indirect-providers-at-this-time-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>ライトハウスにアクセスする際のメッセージ: "Microsoft 365 Lighthouse は、この時点で間接プロバイダーをサポートしない場合、このサービスを使用するには間接リセラーまたは直接請求パートナーである必要があります"

**原因:** 間接請求パートナーとしてライトハウスにアクセスしようとした。 現時点では、ライトハウスは間接リセラーと直接請求パートナーのみをサポートしています。

**解決策:** 条件と要件の完全な一覧については、「要件」を参照 [Microsoft 365 Lighthouse](m365-lighthouse-requirements.md)。 間接プロバイダーではなく、エラーでこのメッセージを受け取ったと思う場合は、サポートにお問い合わせください。 詳細については、「Get [help and support for Microsoft 365 Lighthouse」 を参照してください](m365-lighthouse-get-help-and-support.md)。

### <a name="message-when-trying-to-access-lighthouse-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>ライトハウスにアクセスする場合のメッセージ: "このサービスを使用するには、間接リセラーまたは直接請求パートナーである必要があります"

**原因:** ライトハウスにアクセスしようとしたが、Microsoft パートナーではない。 ライトハウスを使用するには、クラウド ソリューション プロバイダー (CSP) プログラムに間接リセラーまたは直接請求パートナーとして登録する必要があります。

**解決策:** 条件と要件の完全な一覧については、「要件」を参照 [Microsoft 365 Lighthouse](m365-lighthouse-requirements.md)。 ライトハウスにアクセスする資格を持ち、エラーでこのメッセージを受け取ったと思う場合は、サポートにお問い合わせください。 詳細については、「Get [help and support for Microsoft 365 Lighthouse」 を参照してください](m365-lighthouse-get-help-and-support.md)。

### <a name="message-when-signing-in-to-lighthouse-accept-the-partner-amendment"></a>ライトハウスへのサインイン時のメッセージ: "パートナーの修正に同意する"

**原因:** パートナー テナントのグローバル管理者がパートナー修正プログラムに署名する前に、ライトハウスにアクセスしようとした。

**解決策:** グローバル管理者は、ライトハウスにアクセスして作業する前に、ライトハウスにサインインし、パートナーの修正に同意する必要があります。 グローバル管理者が修正に署名した後もエラーが解決しない場合は、サポートにお問い合わせください。 詳細については、「Get [help and support for Microsoft 365 Lighthouse」 を参照してください](m365-lighthouse-get-help-and-support.md)。

## <a name="customer-tenant-onboarding"></a>顧客テナントのオンボーディング  

### <a name="customer-tenants-show-a-status-other-than-active-in-the-tenant-list"></a>顧客テナントは、テナントリストに "Active" 以外の状態を表示します  

**原因:** 顧客テナントが次の条件を満たさなかった。

  - 顧客テナントを管理するには、Managed Service Provider (MSP) に対して委任 (DAP) が設定されている必要があります*
  - 365 Business ライセンスMicrosoft 365 Business PremiumライセンスMicrosoft 365 E3 1 つ以上Windows必要
  - ライセンスユーザーが 1000 人以下である必要があります 

**解決策:** 次の表では、アクションを必要とするさまざまなテナントの状態について説明し、それらを解決する方法について説明します。

*お客様をライトハウスにオンボードするには、代理管理者特権 (DAP) が必要です。 また、より安全な委任アクセスを有効にするには、顧客と一緒に詳細な委任管理者特権 (GDAP) を確立することをお勧めします。 DAP と GDAP が共存する一方で、両方のモデルが配置されている顧客には GDAP が優先されます。 まもなく、GDAP (DAP なし) をお持ちのお客様は、ライトハウスにオンボードできます。<br><br>


| 状態 | 説明 | 解決方法 |
|--|--|--|
| 非アクティブ | テナントは MSP の要求でオフボードされ、ライトハウスで管理されなくなりました。 | テナントを再アクティブ化する必要があります。 [テナント **] ページで** 、再アクティブ化するテナントの横にある 3 つのドット (その他のアクション) を選択し、[テナントのアクティブ化] **を選択します**。 初期顧客データがライトハウスに表示されるには、24 ~ 48 時間かかる場合があります。 |
| 不適格 - DAP または GDAP が設定されていない | テナントに対して DAP または GDAP 管理者特権が設定されている必要はありません。これは、ライトハウスで必要です。 | Microsoft パートナー センターで DAP または GDAP 管理者特権を設定します。 |
| 不適格 - 必須のライセンスが見つからない | テナントに必要なライセンスがありません。 少なくとも 1 つのライセンスまたはMicrosoft 365 Business Premium必要Microsoft 365 E3です。 | テナントに少なくとも 1 つのライセンスまたはMicrosoft 365 Business PremiumがMicrosoft 365 E3してください。 |
| 不適格 - ユーザー数を超えました | テナントには、ライトハウスで許可されているライセンスユーザーが最大 1000 人を超える。 | テナントに 1000 人を超えるライセンスユーザーが存在しない場合は、そのユーザーを確認します。 |
| 不適格 - 地域チェックに失敗しました | ユーザーと顧客は、ライトハウスで必要とされる同じ地理的地域に存在しない。 | 顧客が地理的な地域に存在する可能性を確認します。 そうでなかった場合は、ライトハウスでテナントを管理できません。 |
| プロセス中 | ライトハウスはテナントを検出しましたが、まだオンボーディング中です。 | テナントのオンボーディングを完了するには、ライトハウス 48 時間を許可します。 |

顧客テナントがオンボーディング条件を満たして、まだライトハウスでアクティブとして表示されていないことを確認した場合は、サポートにお問い合わせください。 詳細については、「Get [help and support for Microsoft 365 Lighthouse」 を参照してください](m365-lighthouse-get-help-and-support.md)。

## <a name="access-and-permissions"></a>アクセスとアクセス許可

### <a name="message-when-trying-to-access-lighthouse-not-authorized-or-insufficient-privileges-or-access-restriction-insufficient-or-lack-of-permissions-is-causing-access-restriction"></a>ライトハウスへのアクセスを試みる場合のメッセージ: "Not Authorized" または "不十分な特権" または "アクセス制限: アクセス制限が不足している、またはアクセス制限が発生している" 

**原因:** Azure AD で適切なセキュリティ グループに属していないか、またはライトハウスにアクセスするためにパートナー センターで正しい役割が割り当てられていない。

**解決策:** 適切なアクセス許可を持つパートナー テナントの管理者が、Azure AD の適切な GDAP セキュリティ グループに割り当て、パートナー センターで正しい役割を割り当てしていることを確認します。 また、ライトハウスの一部のアクションでは、グローバル管理者である必要があります。GDAP の役割と各役割で実行できる機能の詳細については、「[Configure Microsoft 365 Lighthouseポータル セキュリティ」を参照してください](m365-lighthouse-configure-portal-security.md)。 GDAP のすべての組み込みAzure ADおよびアクセス許可の詳細については、「組み込みAzure AD[」を参照してください](/azure/active-directory/roles/permissions-reference)。

DAP 関係を持つお客様の場合、パートナー管理者はパートナー センターの管理エージェントまたはヘルプデスク エージェントの役割に割り当てる必要があります。 すべてのパートナー センターの役割とアクセス許可の詳細については、「ユーザーに役割とアクセス許可を割り当てる [」を参照してください](/partner-center/permissions-overview)。

### <a name="i-dont-see-complete-data-in-certain-areas-of-lighthouse-or-i-cant-perform-certain-tasks-or-i-cant-access-certain-tenants"></a>ライトハウスの特定の領域に完全なデータが表示できない、または特定のタスクを実行できない、または特定のテナントにアクセスできない

**原因:** 自分のセキュリティ グループに割り当てられている役割に基Azure AD GDAP アクセスが制限されています。

**解決策:** 適切なアクセス許可を持つパートナー テナントの管理者が、適切な GDAP セキュリティ グループに割り当てられているAzure AD。 また、ライトハウスの一部のアクションでは、グローバル管理者である必要があります。GDAP の役割と各役割で実行できる機能の詳細については、「[Configure Microsoft 365 Lighthouseポータル セキュリティ」を参照してください](m365-lighthouse-configure-portal-security.md)。 GDAP のすべての組み込みAzure ADおよびアクセス許可の詳細については、「組み込みAzure AD[」を参照してください](/azure/active-directory/roles/permissions-reference)。

## <a name="customer-tenant-management"></a>顧客テナント管理  

### <a name="customer-tenant-has-no-data-showing-in-lighthouse"></a>顧客テナントにライトハウスにデータが表示される

**原因:** テナントのオンボーディングが完了する前に、ライトハウスでデータを表示しようとするとします。

**解決策:** 初期顧客データがライトハウスに表示されるには、24 ~ 48 時間かかる場合があります。 テナントのオンボードから 48 時間を超える時間が経ち、テナント データを表示または読み込めない場合や、以前にできたデータを表示または読み込めない場合は、サポートにお問い合わせください。 詳細については、「Get [help and support for Microsoft 365 Lighthouse」 を参照してください](m365-lighthouse-get-help-and-support.md)。 関連するネットワーク ログと、変更された可能性のあるオプションの一覧を提供する準備をしてください。

### <a name="customer-tenant-data-isnt-updating-after-making-changes-in-the-customer-tenant"></a>顧客テナントに変更を加えた後、顧客テナントデータが更新されていない

**原因:** 顧客テナント内で行った変更は、ライトハウスの顧客テナント データとの同期に最大 4 時間かかる場合があります。

**解決策:** 4 時間を超え、顧客テナントのデータがまだライトハウスで更新されていない場合は、サポートにお問い合わせください。 詳細については、「Get [help and support for Microsoft 365 Lighthouse」 を参照してください](m365-lighthouse-get-help-and-support.md)。 顧客テナント情報を提供する準備をしてください。

### <a name="message-when-applying-a-baseline-to-a-customer-tenant-process-error-occurred"></a>顧客テナントにベースラインを適用する場合のメッセージ: "プロセス エラーが発生しました"  

**原因:** 顧客テナント内のサーバーの構成Microsoft Intune完了しなかった。

**解決策:** 顧客テナント内で Intune の基本的な構成手順が完了したと確認します。 顧客テナントの Intune 構成が完了した後も問題が解決しない場合は、サポートにお問い合わせください。 詳細については、「Get [help and support for Microsoft 365 Lighthouse」 を参照してください](m365-lighthouse-get-help-and-support.md)。

### <a name="cant-access-partner-tenant-data-in-lighthouse"></a>ライトハウスのパートナー テナント データにアクセスできない

**原因**: ライトハウスは、顧客テナントの表示 *と管理のみを* サポートしています。 現時点では、パートナー テナントの表示と管理 *は* サポートされていません。

**解決策:** パートナー テナントの表示と管理に使用した方法を引き続き使用します。

## <a name="device-and-threat-management"></a>デバイスと脅威の管理 

### <a name="i-dont-see-any-customer-tenant-data-on-the-device-compliance-and-threat-management-pages-of-lighthouse"></a>ライトハウスの [デバイスコンプライアンス] ページと [脅威管理] ページに顧客テナント データが表示される

**原因 1:** 顧客テナントが Intune へのオンボーディングを完了してない。 顧客テナントの Intune へのオンボーディングが完了するまで、お客様のテナント データは、ライトハウスのデバイスコンプライアンスまたは脅威管理ページでは使用できません。

**解決策:** データを表示しようとしている顧客テナントが Intune へのオンボーディングを完了したことを確認します。 Intune でオンボーディングが完了したら、デバイス データがライトハウスに表示されるのに 4 時間かかります。

**原因 2:** 顧客テナントは最近、ライトハウスにオンボードされ、データはライトハウスで読み込み中です。

**解決策:** 顧客テナントがライトハウスにオンボードされたら、最初の顧客データが表示されるのに 24 ~ 48 時間かかります。

**原因 3:** 顧客テナント デバイスは新しく、デバイス データはライトハウスで読み込み中です。

**解決策:** テナント デバイスが追加されたら、デバイス データがライトハウスに表示されるのに 4 時間かかります。

解決手順に従った後もデバイスコンプライアンスと脅威管理ページにデータが表示されない場合は、サポートにお問い合わせください。 詳細については、「Get [help and support for Microsoft 365 Lighthouse」 を参照してください](m365-lighthouse-get-help-and-support.md)。

## <a name="related-content"></a>関連コンテンツ

[ユーザーに関する既知Microsoft 365 Lighthouse](m365-lighthouse-known-issues.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)\
[ヘルプとサポートを受ける (記事](m365-lighthouse-get-help-and-support.md)Microsoft 365 Lighthouse)