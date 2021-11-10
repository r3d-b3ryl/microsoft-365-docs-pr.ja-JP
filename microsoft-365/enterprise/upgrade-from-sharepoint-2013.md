---
title: 2013 SharePointからのアップグレード
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: sharepoint-server-itpro
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: サーバー 2013 および SharePoint Foundation 2013 SharePointアップグレードする情報とリソースを検索します。 2023 年 4 月 11 日の両方のサポート。
ms.openlocfilehash: 05f545b67d60d6bcc45587049e49a5f5c1f6d654
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889927"
---
# <a name="upgrading-from-sharepoint-2013"></a>2013 SharePointからのアップグレード

2013 Microsoft SharePoint Server 2013 および SharePoint Foundation 2013 の両方が **、2023** 年 4 月 11 日にサポート終了に達します。 この記事では、Microsoft 365 で既存の SharePoint Server データを SharePoint Online に移行したり、オンプレミスの SharePoint 2013 環境をアップグレードしたりするのに役立つリソースを提供します。 この記事の残りの部分については、SharePoint 2013 を使用して、SharePoint Server 2013 と SharePoint Foundation 2013 の両方を参照します。

## <a name="what-is-end-of-support"></a>サポート終了 *とは何ですか*?

ほとんどの Microsoft 製品にはサポート ライフサイクルがあります。その間、新機能、バグ修正、セキュリティ修正などをご利用ください。 サポート終了日が終わると、製品は動作を停止しますが、Microsoft は次の機能を提供しなくなりました。

- 発生する可能性のある問題に対するテクニカル サポート。

- サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。

- サーバーがセキュリティ侵害に対して脆弱になる可能性のある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

つまり、製品のそれ以上の更新プログラム、パッチ、または修正プログラム (セキュリティ パッチ/修正プログラムを含む) はありません。 Microsoft サポートは、サポートの取り組みを、より新しいバージョンに完全に移行します。

> [!NOTE]
> 通常、ソフトウェア ライフサイクルは、最初のリリースから 5 年間のメインストリーム サポートで、さらに 5 年間の延長サポートまで続く可能性があります。 [Microsoft ソリューション プロバイダーは、](https://go.microsoft.com/fwlink/?linkid=841249)次のバージョンのソフトウェアにアップグレードするか、またはソフトウェア (または両方) にMicrosoft 365するのに役立ちます。 重要な基礎となるテクノロジのサポート終了日も、特に SharePoint で使用している Microsoft SQL Server のバージョンに関する情報を確認してください。 詳細については、「固定ライフサイクル ポリシー [」を参照してください](https://support.microsoft.com/help/14085)。

## <a name="plan-ahead"></a>計画を立て

サポートが終了する日付を、SharePoint [Server 2013](/lifecycle/products/sharepoint-server-2013)および SharePoint [Foundation 2013](/lifecycle/products/sharepoint-foundation-2013)で確認します。 これらの日付を念頭に置いてアップグレードまたは移行を計画します。 記載されている日付 *で製品の* 動作が停止しない場合があります。 ただし、インストールは、その日付以降に修正プログラムが適用されなくなるので、製品の次のバージョンへのスムーズな移行を計画する必要があります。 次の表に、使用可能なオプションの一覧を示します。

|サポート製品の終了|Good|良い|高|
|---|---|---|---|
|SharePoint Server 2013<BR>SharePoint Foundation 2013|サーバー 2016 SharePoint 2019 へのアップグレード|SharePoint Server サブスクリプション エディションへのアップグレード|[移行] SharePointでMicrosoft 365

## <a name="whats-next"></a>次の手順

最新のコラボレーション、インテリジェンス、SharePointセキュリティ ソリューションMicrosoft 365活用するために、SharePointのサイトに移行することをお勧Microsoft 365。 最新のエクスペリエンス機能は、Microsoft 365、柔軟性、パフォーマンスに優れたものに設計されています。

オンプレミスの SharePoint 展開を維持する必要がある場合は、Microsoft 365 で SharePoint にできる限り多くの SharePoint 機能を移行できるハイブリッド展開をお勧めします。 ハイブリッド[実装SharePoint計画](/sharepoint/hybrid/hybrid)する方法については、「ハイブリッドの概要」を参照してください。

### <a name="migrate-to-sharepoint-in-microsoft-365"></a>[移行] SharePointでMicrosoft 365

[移行ツール] SharePoint (SPMT) を使用して、サイトとコンテンツをサイト内のSharePoint移行Microsoft 365。 お客様が先に計画し、移行を実行し、発生する可能性がある問題のトラブルシューティングを行う際に役立つ、広範なコンテンツ ライブラリがあります。 [移行ツールSharePoint概要は](/sharepointmigration/introducing-the-sharepoint-migration-tool)、開始する良い場所です。

### <a name="upgrade-to-sharepoint-server-subscription-edition"></a>SharePoint Server サブスクリプション エディションへのアップグレード

SharePoint 2013 年 2013 年からサブスクリプション エディションにアップグレードする直接パスがない場合でも、これは 2 番目に最適なオプションです。 主な理由は、SharePoint Server サブスクリプション エディションが継続的な更新モデルを導入し、今後、新しいメジャー バージョンの SharePointをリリースする必要が無いからです。

サブスクリプション エディションにアップグレードするには、サーバー 2016 または 2019 SharePoint実行している必要があります。 SharePoint 2013 から 2019 への直接パスも存在しなかっていませんので、最善の方法は、最初に 2016 にアップグレードしてからサブスクリプション エディションにアップグレードする方法です。 サブスクリプション エディションへのアップグレードの詳細と計画については、以下のリンクを参照してください。

- [SharePoint Server 2016 へのアップグレード](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [SharePoint Server サブスクリプション エディションへのアップグレード](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-subscription-edition)

オンプレミスの SharePoint 展開を維持する必要がある場合でも、SharePoint ハイブリッド実装を使用してサイトまたはコンテンツの一部を Microsoft 365 に移行して[](/sharepoint/hybrid/hybrid)、Microsoft 365 の最新のコラボレーション エクスペリエンス、セキュリティ、コンプライアンス機能を活用することをお勧めします。  

### <a name="upgrade-to-sharepoint-server-2016-or-2019"></a>サーバー 2016 SharePoint 2019 へのアップグレード

2016 SharePoint 2019 と 2019 の両方が、2013 のサポートの終了を超えてオンプレミスの SharePoint 展開を維持する予定の場合、サポートされるプラットフォームです。 ただし、 **両方のバージョンが 2026** 年 7 月 14 日にサポート終了になります。 つまり、2013 のサポート終了日から 3 年後に別のアップグレードを計画する必要があります。 両方の製品のサポート ライフサイクル ページを次に示します。

- [SharePointServer 2016 サポート ライフサイクルの日付](/lifecycle/products/sharepoint-server-2016)
- [SharePoint Server 2019ライフサイクルの日付をサポートする](/lifecycle/products/sharepoint-server-2019)

アップグレードの詳細と計画については、次の記事を参照してください。

- [SharePoint Server 2016 へのアップグレード](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [SharePoint Server 2019 へのアップグレード](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2019)

オンプレミスの SharePoint 展開を維持する必要がある場合でも、SharePoint ハイブリッド実装を使用してサイトまたはコンテンツの一部を Microsoft 365 に移行して[](/sharepoint/hybrid/hybrid)、Microsoft 365 の最新のコラボレーション エクスペリエンス、セキュリティ、コンプライアンス機能を活用することをお勧めします。  
