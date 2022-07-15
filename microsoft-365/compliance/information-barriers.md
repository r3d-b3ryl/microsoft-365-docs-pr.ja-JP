---
title: 情報バリアについての詳細情報
description: Microsoft Purview の情報バリアについて説明します。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、情報バリア
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4b2a45a667aa654a8ff3111313b542433e692f1f
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66823391"
---
# <a name="learn-about-information-barriers"></a>情報バリアについての詳細情報

Microsoft Purview Information Barriers (IB) は、Microsoft Teams、SharePoint、OneDrive のグループとユーザー間の双方向通信とコラボレーションを制限できるコンプライアンス ソリューションです。 規制の厳しい業界でよく使用される IB は、関心の対立を回避し、ユーザーと組織領域間の内部情報を保護するのに役立ちます。

IB ポリシーが適用されている場合、他の特定のユーザーとファイルの通信や共有を行わないユーザーは、それらのユーザーを検索、選択、チャット、または呼び出すことはできません。 IB ポリシーでは、定義されたグループとユーザー間の不正な通信とコラボレーションを検出して防止するためのチェックが自動的に実施されます。 IB ポリシーは、電子情報開示マネージャーが検索できるユーザー コンテンツの場所を制御する電子情報開示調査の [コンプライアンス境界](/microsoft-365/compliance/set-up-compliance-boundaries) から独立しています。

IB ポリシーでは、次のシナリオ例で、グループとユーザー間の通信とコラボレーションを許可または禁止できます。

- *Day Trader* グループのユーザーは、*マーケティング チーム* とファイルを通信したり共有したりしないでください。
- 会社の機密情報に取り組む財務担当者は、組織内の特定のグループとファイルを通信したり共有したりしないでください
- 営業秘密資料を持つ内部チームは、組織内の特定のグループのユーザーとオンラインで通話したりチャットしたりしないでください。
- リサーチ チームは、製品開発チームとオンラインでのみ通話またはチャットする必要があります
- *Day Trader* グループの SharePoint サイトを、*Day* Trader グループの外部のユーザーが共有したりアクセスしたりしないでください

> [!IMPORTANT]
> 情報バリアでは、双方向の通信とコラボレーションの制限 **のみがサポート** されます。 たとえば、マーケティングが Day Traders と通信して共同作業できるが、Day Traders がマーケティングと通信して共同作業できないシナリオ **はサポートされていません**。

## <a name="information-barriers-and-microsoft-teams"></a>情報バリアと Microsoft Teams

Microsoft Teams では、IB ポリシーによって、次の種類の不正な通信とコラボレーションが決定され、防止されます。

- ユーザーの検索
- チームにメンバーを追加する
- 他のユーザーとのチャット セッションを開始する
- グループ チャットを開始する
- ユーザーを会議に招待する
- 画面を共有する
- 電話をかける
- 別のユーザーとファイルを共有する
- リンクを共有してファイルにアクセスする

Microsoft Teams でこれらのアクティビティを実行しているユーザーが、アクティビティを防止するために IB ポリシーに含まれている場合、ユーザーは続行できません。 さらに、IB ポリシーに含まれるすべてのユーザーが、Microsoft Teams の他のユーザーとの通信をブロックされる可能性があります。 IB ポリシーの影響を受けるユーザーが同じチームまたはグループ チャットの一部である場合は、それらのチャット セッションから削除され、グループとのそれ以上のコミュニケーションが許可されない場合があります。

詳細については、 [Microsoft Teams の情報バリアに関するページを参照してください](/MicrosoftTeams/information-barriers-in-teams)。

## <a name="information-barriers-and-sharepoint-and-onedrive"></a>情報バリアと SharePoint と OneDrive

SharePoint と OneDrive では、IB ポリシーによって、次の種類の承認されていないコラボレーションが検出され、防止されます。

- サイトへのメンバーの追加
- ユーザーによるサイトまたはコンテンツへのアクセス
- 別のユーザーとサイトまたはコンテンツを共有する
- サイトの検索

詳細については、 [SharePoint の情報バリア](/sharepoint/information-barriers) と [OneDrive の情報バリアに関するページを](/onedrive/information-barriers)参照してください。

## <a name="information-barriers-and-exchange-online"></a>情報バリアとExchange Online

IB ポリシーを使用して、電子メール メッセージ内のグループとユーザー間の通信とコラボレーションを制限することはできません。 IB ポリシーは、[Exchange Online アドレス帳ポリシー (ABP) に](/exchange/address-books/address-book-policies/address-book-policies)基づいています。 ABP を使用すると、組織は、組織のグローバル アドレス帳 (GAL) のカスタマイズされたビューを提供するために、ユーザーを特定のグループに仮想的に割り当てることができます。 IB ポリシーが作成されると、ポリシーの ABP が自動的に作成されます。 組織に IB ポリシーが追加されると、GAL の構造と動作は IB ポリシーに準拠するように変更されます。

IB ポリシーを定義して適用する前に、組織内のすべての既存の Exchange アドレス帳ポリシーを削除する必要があります。 IB ポリシーはアドレス帳ポリシーに基づいており、既存の ABPs ポリシーは IB によって作成された ABP と互換性がありません。 既存のアドレス帳ポリシーを削除するには、「[Exchange Onlineでアドレス帳ポリシーを削除する](/exchange/address-books/address-book-policies/remove-an-address-book-policy)」を参照してください。 IB ポリシーが有効になり、階層アドレス帳が有効になっている場合は、IB セグメントに含まれていないすべてのユーザーに、Exchange Online に [階層アドレス帳](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) が表示されます。

現在、IB ポリシーでは、Exchange Onlineデプロイのみがサポートされています。 組織で電子メール通信を定義および制御する必要がある場合は、 [Exchange メール フロー ルール](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)の使用を検討してください。

## <a name="ready-to-get-started"></a>始める準備はいいですか。

- [情報バリアの使用を開始する](information-barriers-policies.md)
- [IB ポリシーを管理する](information-barriers-edit-segments-policies.md)
- [IB ポリシーに使用できる属性を確認する](information-barriers-attributes.md)
