---
title: メールボックス使用率サービスのアラート
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
f1.keywords:
- NOCSH
description: メールボックス使用率サービスアラートを使用して、メールボックスのクォータに達しているメールボックスを監視します。
ms.openlocfilehash: fdc87e92aa6614d78347984cfa09bf75edc131e5
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64935305"
---
# <a name="service-alerts-for-mailbox-utilization-in-exchange-online-monitoring"></a>Exchange Online 監視でのメールボックス使用率サービスのアラート

クォータに達するか、クォータを超えるリスクがあるメールボックスが保留になっていることを通知する新しいExchange Online サービス アラートをリリースしました。 これらのサービス アラートは、管理者の介入を必要とする可能性がある組織内のメールボックスの数を可視化します。

これらのサービス アラートは、Microsoft 365 管理センターに表示されます。 これらのサービス アラートを表示するには、[**正常性** > サービス正常性 **]** に移動し <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">**Exchange Online**</a> > [**アクティブな問題**] タブをクリックします。メールボックス使用率サービスアラートの例を次に示します。

:::image type="content" alt-text="メールボックス使用率サービスアラート。" source="../media/MailboxUtilizationServiceAlert.png" lightbox="../media/MailboxUtilizationServiceAlert.png":::

ストレージ クォータに近づいているメールボックスの一覧 ( *メールボックス使用状況レポート* と呼ばれます) を表示するには、次のスクリーンショットで強調表示されているリンクをクリックします。 このリンクは、サービス アラートに表示されます。

:::image type="content" alt-text="メールボックス使用状況レポートへのリンク。" source="../media/LinkToMailboxUsageReport.png" lightbox="../media/LinkToMailboxUsageReport.png":::

または、メールボックス使用状況レポートへの直接 URL は次のようになります <https://admin.microsoft.com/Adminportal/Home?source=applauncher#/reportsUsage/MailboxUsage>。

## <a name="what-do-these-service-alerts-indicate"></a>これらのサービス アラートは何を示していますか?

メールボックスの使用率に関するサービス アラートは、メールボックスの記憶域クォータに近づいているメールボックスを管理者に通知します。 メールボックスに配置できる保留の種類には、訴訟ホールド、電子情報開示ホールド、Microsoft 365保持ポリシー (データを保持するように構成されている) が含まれます。 メールボックスが保留中の場合、ユーザー (または自動化されたプロセス) は自分のメールボックスからデータを完全に削除できません。 代わりに、管理者は、ユーザーのプライマリ メールボックスからアーカイブ メールボックスにデータを移動するために、Exchange Online (データ保持に関連する組織のコンプライアンス ポリシーとインライン) で MRM アイテム保持ポリシーを構成する必要があります。 保持されているメールボックスが重大または警告状態に達した場合、管理者は [アーカイブ メールボックスを有効に](../compliance/enable-archive-mailboxes.md) し、 [自動拡張アーカイブを有効に](../compliance/enable-autoexpanding-archiving.md) してから、メールボックスに割り当てられたアーカイブ ポリシーの保持期間 (プライマリ メールボックスからアーカイブ メールボックスに電子メールを移動する) が十分に短いことを確認する必要があります。 メールボックス使用率サービスアラートによって識別されるクォータの問題を解決するために何も行わない場合、ユーザーは電子メール メッセージまたは会議出席依頼を送受信できない可能性があります。

メールボックス使用率に関するサービス アラートには、クォータに近づいているメールボックスの数に関するテーブルが含まれています。 次のセクションでは、これらのテーブルの情報と、管理者がこれらのメールボックスがクォータを超えないようにするために実行できるアクションについて説明します。

> [!NOTE]
> サービス アラートには、次のセクションで説明する表の列に表示されるメールボックス クォータプロパティの説明が含まれています。

### <a name="mailboxes-on-hold-without-an-archive"></a>アーカイブのない保留中のメールボックス

次の表は、クォータに近づいているがアーカイブ メールボックスが有効になっていない保留中のメールボックスの数を示しています。 テーブル内の各列は、特定のクォータと、そのクォータに近づいているメールボックスの数を識別します。

| # Mailboxes ProhibitSendReceiveQuota (警告)| # Mailboxes ProhibitSendReceiveQuota (Critical)** |# Mailboxes RecoverableItemsQuota (警告)|# Mailboxes RecoverableItemsQuota (Critical)** |
|:--------------|:--------------|:------------------|:--------------- |
| 2             | 2             | 1                 | 0               |
||||

管理者がこれらのメールボックスに対して実行できるアクションは、アーカイブ メールボックスを有効にして、アイテムがアーカイブ メールボックスに移動されるように、MRM アーカイブ ポリシー (アイテムをアーカイブ メールボックスに移動するExchange Onlineの MRM アイテム保持ポリシー) がメールボックスに適用されるようにすることです。 詳細については、「 [メールボックスのアーカイブポリシーと削除ポリシーを設定する」を](../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)参照してください。

アーカイブ メールボックスを有効にした後は、回復可能なアイテム フォルダーのクォータを増やすことを検討することをお勧めします。 これにより、保留になっているメールボックスの回復可能なアイテム フォルダーのクォータを超えないようにできます。 詳細については、「 [保留メールボックスの回復可能なアイテムのクォータを増やす」を参照してください](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)。

### <a name="mailboxes-on-hold-with-an-archive"></a>アーカイブを含む保留中のメールボックス

次の表に、クォータに近づいていてアーカイブ メールボックスが有効になっている保留中のメールボックスの数を示します。

|# Mailboxes ProhibitSendReceiveQuota (警告) |# Mailboxes ProhibitSendReceiveQuota (Critical) |# Mailboxes RecoverableItemsQuota (警告) |# Mailboxes RecoverableItemsQuota (Critical)** |
|:--------------|:--------------|:------------------|:--------------- |
| 1             | 1             | 6                  | 0               |
||||

管理者がこれらのメールボックスに対して実行できるアクションは、回復可能なアイテム フォルダーのクォータを増やすことです。 詳細については、「 [保留メールボックスの回復可能なアイテムのクォータを増やす」を参照してください](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)。

管理者は、アイテムをアーカイブ メールボックスに移動する MRM アーカイブ ポリシーもメールボックスに適用されていること、およびアーカイブ ポリシーの保持期間が十分に短く、アーカイブに移動する前にアイテムがプライマリ メールボックスに保持される時間が長すぎないようにする必要もあります。

> [!NOTE]
> MRM アーカイブ ポリシーでは、プライマリ メールボックスの回復可能なアイテム フォルダーから、対応するアーカイブ メールボックスの回復可能なアイテム フォルダーにアイテムも移動します。 この機能は、メールボックスが回復可能なアイテムのクォータのクォータを超えないようにするのに役立ちます。

### <a name="mrm-retention-policies-in-your-organization"></a>組織内の MRM アイテム保持ポリシー

メールボックス使用率に関するサービス アラートには、組織内の MRM アイテム保持ポリシーに関する情報と、アイテム保持ポリシーであるメールボックスにアーカイブ メールボックスがあるかどうかを示すテーブルが含まれている場合もあります。 アイテム保持ポリシーの詳細については、「[Exchange Onlineのアイテム保持タグとアイテム保持ポリシー」を](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)参照してください。

| RetentionPolicyGuid | MailboxType | HasMoveDumpsterToArchiveTag | HasMovePrimaryToArchiveTag | HasPersonalArchiveTag |  メールボックス |
|:--------------|:--------------|:---------------|:---------------|:---------------|:--------------- |
| 6c041498-1611-5011-a058-1156ce60890c | PrimaryWithArchive | True | False | True | 398 |
| 6c041498-1611-5011-a058-1156ce60890c | Primary | True | False | True | 10 |
| 749ceecc-d49d-4000-a9d5-594dbaea1e56 | PrimaryWithArchive | False | True | False | 7  |
| 269f6a85-1234-4648-8cde-59bbc7bc67d0 | PrimaryWithArchive | True | True | True | 1 |
| 13fb778d-e1cb-4c44-5768-ad4282906c1f | PrimaryWithArchive | True | True  | False | 1 |
|||||||

次の一覧では、前の表の各列について説明します。

- **RetentionPolicyGuid**: 組織内のメールボックスに割り当てられているアイテム保持ポリシーの GUID。 前の例では、同じアイテム保持ポリシーに対して 2 つの別々の行があります。 最初の行は、ポリシーが割り当てられているアーカイブを含むメールボックスの数を示します。 2 番目の行は、同じポリシーが割り当てられているアーカイブのないメールボックスの数を示します。

   この列に一覧表示されているアイテム保持ポリシーの詳細を取得するには、[powerShell で](/powershell/exchange/connect-to-exchange-online-powershell)次のコマンドExchange Online実行します。

   ```powershell
   Get-RetentionPolicy <GUID> | FL
   ```

   **Name** プロパティの値は、Exchange <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">管理センター</a>の **[アイテム保持ポリシー]** ページに表示されるアイテム保持ポリシーの名前です。

- **MailboxType**: ポリシーが割り当てられているメールボックスの種類を指定します。 値には *、プライマリ* (アーカイブのないメールボックス) または *PrimaryWithArchive* (アーカイブを含むメールボックス) が含まれます。 この列の値が *[プライマリ*] の場合は、ポリシーが割り当てられているメールボックスのアーカイブを有効にする必要があります ( **[メールボックス** ] 列は、これらのメールボックスの数を示します)。 そうしないと、アイテムを移動するアーカイブがないため、アーカイブ ポリシーまたは個人用アーカイブ タグは機能しません。

- **HasMoveDumpsterToArchiveTag**: アイテム保持ポリシーに、プライマリ メールボックスの回復可能なアイテム フォルダー ( *ダンプスター* とも呼ばれます) 内のアイテムをアーカイブ内の回復可能なアイテム フォルダーに移動するアイテム保持タグが含まれていることを示します。 この種類の保持タグは、管理者によって設定されます。回復可能なアイテム タグの保持期間が長すぎる場合は、保持期間を短縮すると、メールボックスが回復可能なアイテム フォルダーのクォータに近づくのを防ぐのに役立ちます。 たとえば、保持期間が 30 日に設定されている場合は、3 日または 5 日に減らすことが役立つ場合があります。  詳細については、「 [保留メールボックスの回復可能なアイテムのクォータを増やす」を参照してください](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)。

- **HasMovePrimaryToArchiveTag**: アイテム保持ポリシーに既定の "アーカイブへの移動" 保持タグ ( *アーカイブ ポリシー* とも呼ばれます) が含まれているかどうかを示します。 この場合、メッセージはプライマリ メールボックス内の通常のフォルダーからアーカイブ メールボックスに移動されます。 この種類の保持タグは、管理者によって設定されます。繰り返しになりますが、このタグの保持期間が短すぎる場合、ユーザーはプライマリ メールボックスのクォータに継続的に到達する際に問題が発生する可能性があります。 アーカイブ ポリシーの保有期間を短縮すると、この問題の解決に役立つ場合があります。

- **HasPersonalArchiveTag**: アイテム保持ポリシーに個人用の "アーカイブへの移動" タグが含まれているかどうかを示します。 アイテム保持ポリシーに個人用の "アーカイブへの移動" タグが含まれている場合、ユーザーはメールボックス内のフォルダーとメッセージにこのタグを適用して、アイテムをアーカイブに移動できます。 ユーザーは、このタグが適用されたフォルダーにメッセージを移動する受信トレイ ルールを設定することもできます。 どちらの場合も、プライマリ メールボックスのクォータに達しないように、アイテムをアーカイブに移動するのに役立ちます。

- **メールボックス**: アイテム保持ポリシーが割り当てられているメールボックスの数 (アーカイブの有無にかかわらず、 **MailboxType** 列に示されているメールボックス) の数を示します。

## <a name="how-often-will-i-see-these-service-alerts"></a>これらのサービス アラートはどのくらいの頻度で表示されますか?

クォータの問題を解決するためのアクションを実行しない場合は、この種類のサービス アラートが 4 日ごとに表示される可能性があります。 それ以降のサービス アラートには、クォータに近づいている他のメールボックスのメールボックス数が多くなる場合があります。 クォータの問題を解決するアクションを実行した場合、このサービス アラートは、クォータの問題がある別のメールボックスが特定された場合にのみ発生します。

## <a name="more-information"></a>詳細情報

- アーカイブ メールボックスの問題のトラブルシューティングと解決については、 [Microsoft Purview のトラブルシューティングに関するページを](/office365/troubleshoot/microsoft-365-compliance-welcome)参照してください。

- メールボックスに配置された保留を特定する方法については、「メールボックス [に配置された保留の種類を特定する方法」を](../compliance/identify-a-hold-on-an-exchange-online-mailbox.md)参照してください。
