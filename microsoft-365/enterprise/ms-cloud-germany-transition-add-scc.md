---
title: Microsoft Cloud Deutschland からの移行中の電子情報開示エクスペリエンスに関する情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- admindeeplinkDEFENDER
description: '概要: Microsoft Cloud Deutschland からの移行に関する電子情報開示移行手順。'
ms.openlocfilehash: 08c44374b834796bce5f624008dd2f7493e7c3f7
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963073"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行中の電子情報開示エクスペリエンスに関する情報
次のセクションでは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行する際の電子情報開示エクスペリエンスに関する追加情報を提供します。

## <a name="ediscovery-administration-until-phase-4"></a>フェーズ 4 までの電子情報開示の管理
フェーズ 4 まで、セキュリティとコンプライアンス センターは完全に利用可能になります。 すべてのコンテンツは引き続き Microsoft Cloud Germany に残り、Microsoft Cloud Germany Security and Compliance Center ( https://protection.office.de/) .

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>フェーズ 4 からフェーズ 9 の終了までの電子情報開示エクスペリエンス
フェーズ 4 の初めからフェーズ 9 が完了するまで、電子情報開示の検索は失敗するか、移行された SharePoint Online、OneDrive for Business、および Exchange Online の場所に対して 0 の結果を返します。

> [!NOTE]
> 移行中、お客様は、コンテンツ検索を含むセキュリティ & コンプライアンス センターでケース、保留、[検索、およびエクスポートを](/microsoft-365/compliance/manage-legal-investigations)[作成し続けます](/microsoft-365/compliance/search-for-content)。 ただし、移行された SharePoint、OneDrive for Business、Exchange Online の場所に対して検索すると、0 の結果が返されるか、エラーが発生します。

移行中に検索で結果がゼロまたはエラーが返された場合は、次のアクションを実行してオンラインSharePointしてください。

- 「ファイルとフォルダーを SharePoint または OneDrive for Business OneDrive からダウンロードする」の手順に従って、SharePoint Online または OneDrive for Business サイトからサイトを直接[SharePointダウンロードします](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)。 このメソッドでは、SharePointの管理者アクセス許可または読み取り専用のアクセス許可が必要です。
- [「OneDrive](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)または SharePoint からファイルとフォルダーをダウンロードする」で説明したように、制限を超えた場合は、SharePoint ファイルと Teams ファイルをコンピューターと同期する[](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)のガイダンスに従って、OneDrive for Business 同期クライアントを使用できます。

- 詳細については、「インプレイス[電子情報開示」を参照Exchange Server。](/Exchange/policy-and-compliance/ediscovery/ediscovery)


## <a name="ediscovery-administration-after-phase-9"></a>フェーズ 9 以降の電子情報開示の管理

**適用対象:** 電子情報開示を使用しているすべてのユーザー

フェーズ 9 では、新しいドイツのデータセンター領域に移行するための最後の手順が完了します。 このフェーズでは、残りのすべてのサービス コンポーネントが移行されます。
フェーズ 9 の後、Microsoft Cloud Germany (protection.office.de) のセキュリティとコンプライアンス センターの使用はサポートされなくなりました。 代わりに、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">新Microsoft 365セキュリティ センター</a><a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">またはMicrosoft 365 コンプライアンス センター</a>使用します。 すべてのデータが新しい管理ポータルに移行されました。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
|  すべての SharePoint、OneDrive for Business、およびExchange Onlineの場所は、セキュリティとコンプライアンス センター (SCC) と共に移行されています。 | すべての電子情報開示アクティビティは、世界中のテナントから実行する必要があります。 これで、検索は 100% 成功します。 エラーやエラーは、通常のサポート チャネルに従う必要があります。 | なし |
||||

### <a name="ediscovery-retention-policy"></a>電子情報開示の保持ポリシー
**適用対象:**  移行前の手順の一部としてアイテム保持ポリシーを適用したすべての顧客

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 移行前の手順で作成された組織全体の保持ポリシーを削除する | 顧客は、移行前の作業中に作成された組織全体の保持ポリシーを削除できます。 | なし |
||||
