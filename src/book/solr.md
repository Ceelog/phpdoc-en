Apache Solr
===========

**Table of Contents**

-   [Introduction](/intro/solr.html)
-   [Installing/Configuring](/solr/setup.html)
    -   [Requirements](/solr/setup.html#Requirements)
    -   [Installation](/solr/setup.html#Installation)
    -   [Runtime
        Configuration](/solr/setup.html#Runtime%20Configuration)
    -   [Resource Types](/solr/setup.html#Resource%20Types)
-   [Predefined Constants](/solr/constants.html)
-   [Solr Functions](/ref/solr.html)
    -   [solr\_get\_version](/ref/solr.html#solr_get_version) — Returns
        the current version of the Apache Solr extension
-   [Examples](/solr/examples.html)
-   [SolrUtils](/class/solrutils.html) — The SolrUtils class
    -   [SolrUtils::digestXmlResponse](/class/solrutils.html#SolrUtils::digestXmlResponse)
        — Parses an response XML string into a SolrObject
    -   [SolrUtils::escapeQueryChars](/class/solrutils.html#SolrUtils::escapeQueryChars)
        — Escapes a lucene query string
    -   [SolrUtils::getSolrVersion](/class/solrutils.html#SolrUtils::getSolrVersion)
        — Returns the current version of the Solr extension
    -   [SolrUtils::queryPhrase](/class/solrutils.html#SolrUtils::queryPhrase)
        — Prepares a phrase from an unescaped lucene string
-   [SolrInputDocument](/class/solrinputdocument.html) — The
    SolrInputDocument class
    -   [SolrInputDocument::addChildDocument](/class/solrinputdocument.html#SolrInputDocument::addChildDocument)
        — Adds a child document for block indexing
    -   [SolrInputDocument::addChildDocuments](/class/solrinputdocument.html#SolrInputDocument::addChildDocuments)
        — Adds an array of child documents
    -   [SolrInputDocument::addField](/class/solrinputdocument.html#SolrInputDocument::addField)
        — Adds a field to the document
    -   [SolrInputDocument::clear](/class/solrinputdocument.html#SolrInputDocument::clear)
        — Resets the input document
    -   [SolrInputDocument::\_\_clone](/class/solrinputdocument.html#SolrInputDocument::__clone)
        — Creates a copy of a SolrDocument
    -   [SolrInputDocument::\_\_construct](/class/solrinputdocument.html#SolrInputDocument::__construct)
        — Constructor
    -   [SolrInputDocument::deleteField](/class/solrinputdocument.html#SolrInputDocument::deleteField)
        — Removes a field from the document
    -   [SolrInputDocument::\_\_destruct](/class/solrinputdocument.html#SolrInputDocument::__destruct)
        — Destructor
    -   [SolrInputDocument::fieldExists](/class/solrinputdocument.html#SolrInputDocument::fieldExists)
        — Checks if a field exists
    -   [SolrInputDocument::getBoost](/class/solrinputdocument.html#SolrInputDocument::getBoost)
        — Retrieves the current boost value for the document
    -   [SolrInputDocument::getChildDocuments](/class/solrinputdocument.html#SolrInputDocument::getChildDocuments)
        — Returns an array of child documents (SolrInputDocument)
    -   [SolrInputDocument::getChildDocumentsCount](/class/solrinputdocument.html#SolrInputDocument::getChildDocumentsCount)
        — Returns the number of child documents
    -   [SolrInputDocument::getField](/class/solrinputdocument.html#SolrInputDocument::getField)
        — Retrieves a field by name
    -   [SolrInputDocument::getFieldBoost](/class/solrinputdocument.html#SolrInputDocument::getFieldBoost)
        — Retrieves the boost value for a particular field
    -   [SolrInputDocument::getFieldCount](/class/solrinputdocument.html#SolrInputDocument::getFieldCount)
        — Returns the number of fields in the document
    -   [SolrInputDocument::getFieldNames](/class/solrinputdocument.html#SolrInputDocument::getFieldNames)
        — Returns an array containing all the fields in the document
    -   [SolrInputDocument::hasChildDocuments](/class/solrinputdocument.html#SolrInputDocument::hasChildDocuments)
        — Returns true if the document has any child documents
    -   [SolrInputDocument::merge](/class/solrinputdocument.html#SolrInputDocument::merge)
        — Merges one input document into another
    -   [SolrInputDocument::reset](/class/solrinputdocument.html#SolrInputDocument::reset)
        — This is an alias of SolrInputDocument::clear
    -   [SolrInputDocument::setBoost](/class/solrinputdocument.html#SolrInputDocument::setBoost)
        — Sets the boost value for this document
    -   [SolrInputDocument::setFieldBoost](/class/solrinputdocument.html#SolrInputDocument::setFieldBoost)
        — Sets the index-time boost value for a field
    -   [SolrInputDocument::sort](/class/solrinputdocument.html#SolrInputDocument::sort)
        — Sorts the fields within the document
    -   [SolrInputDocument::toArray](/class/solrinputdocument.html#SolrInputDocument::toArray)
        — Returns an array representation of the input document
-   [SolrDocument](/class/solrdocument.html) — The SolrDocument class
    -   [SolrDocument::addField](/class/solrdocument.html#SolrDocument::addField)
        — Adds a field to the document
    -   [SolrDocument::clear](/class/solrdocument.html#SolrDocument::clear)
        — Drops all the fields in the document
    -   [SolrDocument::\_\_clone](/class/solrdocument.html#SolrDocument::__clone)
        — Creates a copy of a SolrDocument object
    -   [SolrDocument::\_\_construct](/class/solrdocument.html#SolrDocument::__construct)
        — Constructor
    -   [SolrDocument::current](/class/solrdocument.html#SolrDocument::current)
        — Retrieves the current field
    -   [SolrDocument::deleteField](/class/solrdocument.html#SolrDocument::deleteField)
        — Removes a field from the document
    -   [SolrDocument::\_\_destruct](/class/solrdocument.html#SolrDocument::__destruct)
        — Destructor
    -   [SolrDocument::fieldExists](/class/solrdocument.html#SolrDocument::fieldExists)
        — Checks if a field exists in the document
    -   [SolrDocument::\_\_get](/class/solrdocument.html#SolrDocument::__get)
        — Access the field as a property
    -   [SolrDocument::getChildDocuments](/class/solrdocument.html#SolrDocument::getChildDocuments)
        — Returns an array of child documents (SolrDocument)
    -   [SolrDocument::getChildDocumentsCount](/class/solrdocument.html#SolrDocument::getChildDocumentsCount)
        — Returns the number of child documents
    -   [SolrDocument::getField](/class/solrdocument.html#SolrDocument::getField)
        — Retrieves a field by name
    -   [SolrDocument::getFieldCount](/class/solrdocument.html#SolrDocument::getFieldCount)
        — Returns the number of fields in this document
    -   [SolrDocument::getFieldNames](/class/solrdocument.html#SolrDocument::getFieldNames)
        — Returns an array of fields names in the document
    -   [SolrDocument::getInputDocument](/class/solrdocument.html#SolrDocument::getInputDocument)
        — Returns a SolrInputDocument equivalent of the object
    -   [SolrDocument::hasChildDocuments](/class/solrdocument.html#SolrDocument::hasChildDocuments)
        — Checks whether the document has any child documents
    -   [SolrDocument::\_\_isset](/class/solrdocument.html#SolrDocument::__isset)
        — Checks if a field exists
    -   [SolrDocument::key](/class/solrdocument.html#SolrDocument::key)
        — Retrieves the current key
    -   [SolrDocument::merge](/class/solrdocument.html#SolrDocument::merge)
        — Merges source to the current SolrDocument
    -   [SolrDocument::next](/class/solrdocument.html#SolrDocument::next)
        — Moves the internal pointer to the next field
    -   [SolrDocument::offsetExists](/class/solrdocument.html#SolrDocument::offsetExists)
        — Checks if a particular field exists
    -   [SolrDocument::offsetGet](/class/solrdocument.html#SolrDocument::offsetGet)
        — Retrieves a field
    -   [SolrDocument::offsetSet](/class/solrdocument.html#SolrDocument::offsetSet)
        — Adds a field to the document
    -   [SolrDocument::offsetUnset](/class/solrdocument.html#SolrDocument::offsetUnset)
        — Removes a field
    -   [SolrDocument::reset](/class/solrdocument.html#SolrDocument::reset)
        — This is an alias to SolrDocument::clear()
    -   [SolrDocument::rewind](/class/solrdocument.html#SolrDocument::rewind)
        — Resets the internal pointer to the beginning
    -   [SolrDocument::serialize](/class/solrdocument.html#SolrDocument::serialize)
        — Used for custom serialization
    -   [SolrDocument::\_\_set](/class/solrdocument.html#SolrDocument::__set)
        — Adds another field to the document
    -   [SolrDocument::sort](/class/solrdocument.html#SolrDocument::sort)
        — Sorts the fields in the document
    -   [SolrDocument::toArray](/class/solrdocument.html#SolrDocument::toArray)
        — Returns an array representation of the document
    -   [SolrDocument::unserialize](/class/solrdocument.html#SolrDocument::unserialize)
        — Custom serialization of SolrDocument objects
    -   [SolrDocument::\_\_unset](/class/solrdocument.html#SolrDocument::__unset)
        — Removes a field from the document
    -   [SolrDocument::valid](/class/solrdocument.html#SolrDocument::valid)
        — Checks if the current position internally is still valid
-   [SolrDocumentField](/class/solrdocumentfield.html) — The
    SolrDocumentField class
    -   [SolrDocumentField::\_\_construct](/class/solrdocumentfield.html#SolrDocumentField::__construct)
        — Constructor
    -   [SolrDocumentField::\_\_destruct](/class/solrdocumentfield.html#SolrDocumentField::__destruct)
        — Destructor
-   [SolrObject](/class/solrobject.html) — The SolrObject class
    -   [SolrObject::\_\_construct](/class/solrobject.html#SolrObject::__construct)
        — Creates Solr object
    -   [SolrObject::\_\_destruct](/class/solrobject.html#SolrObject::__destruct)
        — Destructor
    -   [SolrObject::getPropertyNames](/class/solrobject.html#SolrObject::getPropertyNames)
        — Returns an array of all the names of the properties
    -   [SolrObject::offsetExists](/class/solrobject.html#SolrObject::offsetExists)
        — Checks if the property exists
    -   [SolrObject::offsetGet](/class/solrobject.html#SolrObject::offsetGet)
        — Used to retrieve a property
    -   [SolrObject::offsetSet](/class/solrobject.html#SolrObject::offsetSet)
        — Sets the value for a property
    -   [SolrObject::offsetUnset](/class/solrobject.html#SolrObject::offsetUnset)
        — Unsets the value for the property
-   [SolrClient](/class/solrclient.html) — The SolrClient class
    -   [SolrClient::addDocument](/class/solrclient.html#SolrClient::addDocument)
        — Adds a document to the index
    -   [SolrClient::addDocuments](/class/solrclient.html#SolrClient::addDocuments)
        — Adds a collection of SolrInputDocument instances to the index
    -   [SolrClient::commit](/class/solrclient.html#SolrClient::commit)
        — Finalizes all add/deletes made to the index
    -   [SolrClient::\_\_construct](/class/solrclient.html#SolrClient::__construct)
        — Constructor for the SolrClient object
    -   [SolrClient::deleteById](/class/solrclient.html#SolrClient::deleteById)
        — Delete by Id
    -   [SolrClient::deleteByIds](/class/solrclient.html#SolrClient::deleteByIds)
        — Deletes by Ids
    -   [SolrClient::deleteByQueries](/class/solrclient.html#SolrClient::deleteByQueries)
        — Removes all documents matching any of the queries
    -   [SolrClient::deleteByQuery](/class/solrclient.html#SolrClient::deleteByQuery)
        — Deletes all documents matching the given query
    -   [SolrClient::\_\_destruct](/class/solrclient.html#SolrClient::__destruct)
        — Destructor for SolrClient
    -   [SolrClient::getById](/class/solrclient.html#SolrClient::getById)
        — Get Document By Id. Utilizes Solr Realtime Get (RTG)
    -   [SolrClient::getByIds](/class/solrclient.html#SolrClient::getByIds)
        — Get Documents by their Ids. Utilizes Solr Realtime Get (RTG)
    -   [SolrClient::getDebug](/class/solrclient.html#SolrClient::getDebug)
        — Returns the debug data for the last connection attempt
    -   [SolrClient::getOptions](/class/solrclient.html#SolrClient::getOptions)
        — Returns the client options set internally
    -   [SolrClient::optimize](/class/solrclient.html#SolrClient::optimize)
        — Defragments the index
    -   [SolrClient::ping](/class/solrclient.html#SolrClient::ping) —
        Checks if Solr server is still up
    -   [SolrClient::query](/class/solrclient.html#SolrClient::query) —
        Sends a query to the server
    -   [SolrClient::request](/class/solrclient.html#SolrClient::request)
        — Sends a raw update request
    -   [SolrClient::rollback](/class/solrclient.html#SolrClient::rollback)
        — Rollbacks all add/deletes made to the index since the last
        commit
    -   [SolrClient::setResponseWriter](/class/solrclient.html#SolrClient::setResponseWriter)
        — Sets the response writer used to prepare the response from
        Solr
    -   [SolrClient::setServlet](/class/solrclient.html#SolrClient::setServlet)
        — Changes the specified servlet type to a new value
    -   [SolrClient::system](/class/solrclient.html#SolrClient::system)
        — Retrieve Solr Server information
    -   [SolrClient::threads](/class/solrclient.html#SolrClient::threads)
        — Checks the threads status
-   [SolrResponse](/class/solrresponse.html) — The SolrResponse class
    -   [SolrResponse::getDigestedResponse](/class/solrresponse.html#SolrResponse::getDigestedResponse)
        — Returns the XML response as serialized PHP data
    -   [SolrResponse::getHttpStatus](/class/solrresponse.html#SolrResponse::getHttpStatus)
        — Returns the HTTP status of the response
    -   [SolrResponse::getHttpStatusMessage](/class/solrresponse.html#SolrResponse::getHttpStatusMessage)
        — Returns more details on the HTTP status
    -   [SolrResponse::getRawRequest](/class/solrresponse.html#SolrResponse::getRawRequest)
        — Returns the raw request sent to the Solr server
    -   [SolrResponse::getRawRequestHeaders](/class/solrresponse.html#SolrResponse::getRawRequestHeaders)
        — Returns the raw request headers sent to the Solr server
    -   [SolrResponse::getRawResponse](/class/solrresponse.html#SolrResponse::getRawResponse)
        — Returns the raw response from the server
    -   [SolrResponse::getRawResponseHeaders](/class/solrresponse.html#SolrResponse::getRawResponseHeaders)
        — Returns the raw response headers from the server
    -   [SolrResponse::getRequestUrl](/class/solrresponse.html#SolrResponse::getRequestUrl)
        — Returns the full URL the request was sent to
    -   [SolrResponse::getResponse](/class/solrresponse.html#SolrResponse::getResponse)
        — Returns a SolrObject representing the XML response from the
        server
    -   [SolrResponse::setParseMode](/class/solrresponse.html#SolrResponse::setParseMode)
        — Sets the parse mode
    -   [SolrResponse::success](/class/solrresponse.html#SolrResponse::success)
        — Was the request a success
-   [SolrQueryResponse](/class/solrqueryresponse.html) — The
    SolrQueryResponse class
    -   [SolrQueryResponse::\_\_construct](/class/solrqueryresponse.html#SolrQueryResponse::__construct)
        — Constructor
    -   [SolrQueryResponse::\_\_destruct](/class/solrqueryresponse.html#SolrQueryResponse::__destruct)
        — Destructor
-   [SolrUpdateResponse](/class/solrupdateresponse.html) — The
    SolrUpdateResponse class
    -   [SolrUpdateResponse::\_\_construct](/class/solrupdateresponse.html#SolrUpdateResponse::__construct)
        — Constructor
    -   [SolrUpdateResponse::\_\_destruct](/class/solrupdateresponse.html#SolrUpdateResponse::__destruct)
        — Destructor
-   [SolrPingResponse](/class/solrpingresponse.html) — The
    SolrPingResponse class
    -   [SolrPingResponse::\_\_construct](/class/solrpingresponse.html#SolrPingResponse::__construct)
        — Constructor
    -   [SolrPingResponse::\_\_destruct](/class/solrpingresponse.html#SolrPingResponse::__destruct)
        — Destructor
    -   [SolrPingResponse::getResponse](/class/solrpingresponse.html#SolrPingResponse::getResponse)
        — Returns the response from the server
-   [SolrGenericResponse](/class/solrgenericresponse.html) — The
    SolrGenericResponse class
    -   [SolrGenericResponse::\_\_construct](/class/solrgenericresponse.html#SolrGenericResponse::__construct)
        — Constructor
    -   [SolrGenericResponse::\_\_destruct](/class/solrgenericresponse.html#SolrGenericResponse::__destruct)
        — Destructor
-   [SolrParams](/class/solrparams.html) — The SolrParams class
    -   [SolrParams::add](/class/solrparams.html#SolrParams::add) — This
        is an alias for SolrParams::addParam
    -   [SolrParams::addParam](/class/solrparams.html#SolrParams::addParam)
        — Adds a parameter to the object
    -   [SolrParams::get](/class/solrparams.html#SolrParams::get) — This
        is an alias for SolrParams::getParam
    -   [SolrParams::getParam](/class/solrparams.html#SolrParams::getParam)
        — Returns a parameter value
    -   [SolrParams::getParams](/class/solrparams.html#SolrParams::getParams)
        — Returns an array of non URL-encoded parameters
    -   [SolrParams::getPreparedParams](/class/solrparams.html#SolrParams::getPreparedParams)
        — Returns an array of URL-encoded parameters
    -   [SolrParams::serialize](/class/solrparams.html#SolrParams::serialize)
        — Used for custom serialization
    -   [SolrParams::set](/class/solrparams.html#SolrParams::set) — An
        alias of SolrParams::setParam
    -   [SolrParams::setParam](/class/solrparams.html#SolrParams::setParam)
        — Sets the parameter to the specified value
    -   [SolrParams::toString](/class/solrparams.html#SolrParams::toString)
        — Returns all the name-value pair parameters in the object
    -   [SolrParams::unserialize](/class/solrparams.html#SolrParams::unserialize)
        — Used for custom serialization
-   [SolrModifiableParams](/class/solrmodifiableparams.html) — The
    SolrModifiableParams class
    -   [SolrModifiableParams::\_\_construct](/class/solrmodifiableparams.html#SolrModifiableParams::__construct)
        — Constructor
    -   [SolrModifiableParams::\_\_destruct](/class/solrmodifiableparams.html#SolrModifiableParams::__destruct)
        — Destructor
-   [SolrQuery](/class/solrquery.html) — The SolrQuery class
    -   [SolrQuery::addExpandFilterQuery](/class/solrquery.html#SolrQuery::addExpandFilterQuery)
        — Overrides main filter query, determines which documents to
        include in the main group
    -   [SolrQuery::addExpandSortField](/class/solrquery.html#SolrQuery::addExpandSortField)
        — Orders the documents within the expanded groups (expand.sort
        parameter)
    -   [SolrQuery::addFacetDateField](/class/solrquery.html#SolrQuery::addFacetDateField)
        — Maps to facet.date
    -   [SolrQuery::addFacetDateOther](/class/solrquery.html#SolrQuery::addFacetDateOther)
        — Adds another facet.date.other parameter
    -   [SolrQuery::addFacetField](/class/solrquery.html#SolrQuery::addFacetField)
        — Adds another field to the facet
    -   [SolrQuery::addFacetQuery](/class/solrquery.html#SolrQuery::addFacetQuery)
        — Adds a facet query
    -   [SolrQuery::addField](/class/solrquery.html#SolrQuery::addField)
        — Specifies which fields to return in the result
    -   [SolrQuery::addFilterQuery](/class/solrquery.html#SolrQuery::addFilterQuery)
        — Specifies a filter query
    -   [SolrQuery::addGroupField](/class/solrquery.html#SolrQuery::addGroupField)
        — Add a field to be used to group results
    -   [SolrQuery::addGroupFunction](/class/solrquery.html#SolrQuery::addGroupFunction)
        — Allows grouping results based on the unique values of a
        function query (group.func parameter)
    -   [SolrQuery::addGroupQuery](/class/solrquery.html#SolrQuery::addGroupQuery)
        — Allows grouping of documents that match the given query
    -   [SolrQuery::addGroupSortField](/class/solrquery.html#SolrQuery::addGroupSortField)
        — Add a group sort field (group.sort parameter)
    -   [SolrQuery::addHighlightField](/class/solrquery.html#SolrQuery::addHighlightField)
        — Maps to hl.fl
    -   [SolrQuery::addMltField](/class/solrquery.html#SolrQuery::addMltField)
        — Sets a field to use for similarity
    -   [SolrQuery::addMltQueryField](/class/solrquery.html#SolrQuery::addMltQueryField)
        — Maps to mlt.qf
    -   [SolrQuery::addSortField](/class/solrquery.html#SolrQuery::addSortField)
        — Used to control how the results should be sorted
    -   [SolrQuery::addStatsFacet](/class/solrquery.html#SolrQuery::addStatsFacet)
        — Requests a return of sub results for values within the given
        facet
    -   [SolrQuery::addStatsField](/class/solrquery.html#SolrQuery::addStatsField)
        — Maps to stats.field parameter
    -   [SolrQuery::collapse](/class/solrquery.html#SolrQuery::collapse)
        — Collapses the result set to a single document per group
    -   [SolrQuery::\_\_construct](/class/solrquery.html#SolrQuery::__construct)
        — Constructor
    -   [SolrQuery::\_\_destruct](/class/solrquery.html#SolrQuery::__destruct)
        — Destructor
    -   [SolrQuery::getExpand](/class/solrquery.html#SolrQuery::getExpand)
        — Returns true if group expanding is enabled
    -   [SolrQuery::getExpandFilterQueries](/class/solrquery.html#SolrQuery::getExpandFilterQueries)
        — Returns the expand filter queries
    -   [SolrQuery::getExpandQuery](/class/solrquery.html#SolrQuery::getExpandQuery)
        — Returns the expand query expand.q parameter
    -   [SolrQuery::getExpandRows](/class/solrquery.html#SolrQuery::getExpandRows)
        — Returns The number of rows to display in each group
        (expand.rows)
    -   [SolrQuery::getExpandSortFields](/class/solrquery.html#SolrQuery::getExpandSortFields)
        — Returns an array of fields
    -   [SolrQuery::getFacet](/class/solrquery.html#SolrQuery::getFacet)
        — Returns the value of the facet parameter
    -   [SolrQuery::getFacetDateEnd](/class/solrquery.html#SolrQuery::getFacetDateEnd)
        — Returns the value for the facet.date.end parameter
    -   [SolrQuery::getFacetDateFields](/class/solrquery.html#SolrQuery::getFacetDateFields)
        — Returns all the facet.date fields
    -   [SolrQuery::getFacetDateGap](/class/solrquery.html#SolrQuery::getFacetDateGap)
        — Returns the value of the facet.date.gap parameter
    -   [SolrQuery::getFacetDateHardEnd](/class/solrquery.html#SolrQuery::getFacetDateHardEnd)
        — Returns the value of the facet.date.hardend parameter
    -   [SolrQuery::getFacetDateOther](/class/solrquery.html#SolrQuery::getFacetDateOther)
        — Returns the value for the facet.date.other parameter
    -   [SolrQuery::getFacetDateStart](/class/solrquery.html#SolrQuery::getFacetDateStart)
        — Returns the lower bound for the first date range for all date
        faceting on this field
    -   [SolrQuery::getFacetFields](/class/solrquery.html#SolrQuery::getFacetFields)
        — Returns all the facet fields
    -   [SolrQuery::getFacetLimit](/class/solrquery.html#SolrQuery::getFacetLimit)
        — Returns the maximum number of constraint counts that should be
        returned for the facet fields
    -   [SolrQuery::getFacetMethod](/class/solrquery.html#SolrQuery::getFacetMethod)
        — Returns the value of the facet.method parameter
    -   [SolrQuery::getFacetMinCount](/class/solrquery.html#SolrQuery::getFacetMinCount)
        — Returns the minimum counts for facet fields should be included
        in the response
    -   [SolrQuery::getFacetMissing](/class/solrquery.html#SolrQuery::getFacetMissing)
        — Returns the current state of the facet.missing parameter
    -   [SolrQuery::getFacetOffset](/class/solrquery.html#SolrQuery::getFacetOffset)
        — Returns an offset into the list of constraints to be used for
        pagination
    -   [SolrQuery::getFacetPrefix](/class/solrquery.html#SolrQuery::getFacetPrefix)
        — Returns the facet prefix
    -   [SolrQuery::getFacetQueries](/class/solrquery.html#SolrQuery::getFacetQueries)
        — Returns all the facet queries
    -   [SolrQuery::getFacetSort](/class/solrquery.html#SolrQuery::getFacetSort)
        — Returns the facet sort type
    -   [SolrQuery::getFields](/class/solrquery.html#SolrQuery::getFields)
        — Returns the list of fields that will be returned in the
        response
    -   [SolrQuery::getFilterQueries](/class/solrquery.html#SolrQuery::getFilterQueries)
        — Returns an array of filter queries
    -   [SolrQuery::getGroup](/class/solrquery.html#SolrQuery::getGroup)
        — Returns true if grouping is enabled
    -   [SolrQuery::getGroupCachePercent](/class/solrquery.html#SolrQuery::getGroupCachePercent)
        — Returns group cache percent value
    -   [SolrQuery::getGroupFacet](/class/solrquery.html#SolrQuery::getGroupFacet)
        — Returns the group.facet parameter value
    -   [SolrQuery::getGroupFields](/class/solrquery.html#SolrQuery::getGroupFields)
        — Returns group fields (group.field parameter values)
    -   [SolrQuery::getGroupFormat](/class/solrquery.html#SolrQuery::getGroupFormat)
        — Returns the group.format value
    -   [SolrQuery::getGroupFunctions](/class/solrquery.html#SolrQuery::getGroupFunctions)
        — Returns group functions (group.func parameter values)
    -   [SolrQuery::getGroupLimit](/class/solrquery.html#SolrQuery::getGroupLimit)
        — Returns the group.limit value
    -   [SolrQuery::getGroupMain](/class/solrquery.html#SolrQuery::getGroupMain)
        — Returns the group.main value
    -   [SolrQuery::getGroupNGroups](/class/solrquery.html#SolrQuery::getGroupNGroups)
        — Returns the group.ngroups value
    -   [SolrQuery::getGroupOffset](/class/solrquery.html#SolrQuery::getGroupOffset)
        — Returns the group.offset value
    -   [SolrQuery::getGroupQueries](/class/solrquery.html#SolrQuery::getGroupQueries)
        — Returns all the group.query parameter values
    -   [SolrQuery::getGroupSortFields](/class/solrquery.html#SolrQuery::getGroupSortFields)
        — Returns the group.sort value
    -   [SolrQuery::getGroupTruncate](/class/solrquery.html#SolrQuery::getGroupTruncate)
        — Returns the group.truncate value
    -   [SolrQuery::getHighlight](/class/solrquery.html#SolrQuery::getHighlight)
        — Returns the state of the hl parameter
    -   [SolrQuery::getHighlightAlternateField](/class/solrquery.html#SolrQuery::getHighlightAlternateField)
        — Returns the highlight field to use as backup or default
    -   [SolrQuery::getHighlightFields](/class/solrquery.html#SolrQuery::getHighlightFields)
        — Returns all the fields that Solr should generate highlighted
        snippets for
    -   [SolrQuery::getHighlightFormatter](/class/solrquery.html#SolrQuery::getHighlightFormatter)
        — Returns the formatter for the highlighted output
    -   [SolrQuery::getHighlightFragmenter](/class/solrquery.html#SolrQuery::getHighlightFragmenter)
        — Returns the text snippet generator for highlighted text
    -   [SolrQuery::getHighlightFragsize](/class/solrquery.html#SolrQuery::getHighlightFragsize)
        — Returns the number of characters of fragments to consider for
        highlighting
    -   [SolrQuery::getHighlightHighlightMultiTerm](/class/solrquery.html#SolrQuery::getHighlightHighlightMultiTerm)
        — Returns whether or not to enable highlighting for
        range/wildcard/fuzzy/prefix queries
    -   [SolrQuery::getHighlightMaxAlternateFieldLength](/class/solrquery.html#SolrQuery::getHighlightMaxAlternateFieldLength)
        — Returns the maximum number of characters of the field to
        return
    -   [SolrQuery::getHighlightMaxAnalyzedChars](/class/solrquery.html#SolrQuery::getHighlightMaxAnalyzedChars)
        — Returns the maximum number of characters into a document to
        look for suitable snippets
    -   [SolrQuery::getHighlightMergeContiguous](/class/solrquery.html#SolrQuery::getHighlightMergeContiguous)
        — Returns whether or not the collapse contiguous fragments into
        a single fragment
    -   [SolrQuery::getHighlightRegexMaxAnalyzedChars](/class/solrquery.html#SolrQuery::getHighlightRegexMaxAnalyzedChars)
        — Returns the maximum number of characters from a field when
        using the regex fragmenter
    -   [SolrQuery::getHighlightRegexPattern](/class/solrquery.html#SolrQuery::getHighlightRegexPattern)
        — Returns the regular expression for fragmenting
    -   [SolrQuery::getHighlightRegexSlop](/class/solrquery.html#SolrQuery::getHighlightRegexSlop)
        — Returns the deviation factor from the ideal fragment size
    -   [SolrQuery::getHighlightRequireFieldMatch](/class/solrquery.html#SolrQuery::getHighlightRequireFieldMatch)
        — Returns if a field will only be highlighted if the query
        matched in this particular field
    -   [SolrQuery::getHighlightSimplePost](/class/solrquery.html#SolrQuery::getHighlightSimplePost)
        — Returns the text which appears after a highlighted term
    -   [SolrQuery::getHighlightSimplePre](/class/solrquery.html#SolrQuery::getHighlightSimplePre)
        — Returns the text which appears before a highlighted term
    -   [SolrQuery::getHighlightSnippets](/class/solrquery.html#SolrQuery::getHighlightSnippets)
        — Returns the maximum number of highlighted snippets to generate
        per field
    -   [SolrQuery::getHighlightUsePhraseHighlighter](/class/solrquery.html#SolrQuery::getHighlightUsePhraseHighlighter)
        — Returns the state of the hl.usePhraseHighlighter parameter
    -   [SolrQuery::getMlt](/class/solrquery.html#SolrQuery::getMlt) —
        Returns whether or not MoreLikeThis results should be enabled
    -   [SolrQuery::getMltBoost](/class/solrquery.html#SolrQuery::getMltBoost)
        — Returns whether or not the query will be boosted by the
        interesting term relevance
    -   [SolrQuery::getMltCount](/class/solrquery.html#SolrQuery::getMltCount)
        — Returns the number of similar documents to return for each
        result
    -   [SolrQuery::getMltFields](/class/solrquery.html#SolrQuery::getMltFields)
        — Returns all the fields to use for similarity
    -   [SolrQuery::getMltMaxNumQueryTerms](/class/solrquery.html#SolrQuery::getMltMaxNumQueryTerms)
        — Returns the maximum number of query terms that will be
        included in any generated query
    -   [SolrQuery::getMltMaxNumTokens](/class/solrquery.html#SolrQuery::getMltMaxNumTokens)
        — Returns the maximum number of tokens to parse in each document
        field that is not stored with TermVector support
    -   [SolrQuery::getMltMaxWordLength](/class/solrquery.html#SolrQuery::getMltMaxWordLength)
        — Returns the maximum word length above which words will be
        ignored
    -   [SolrQuery::getMltMinDocFrequency](/class/solrquery.html#SolrQuery::getMltMinDocFrequency)
        — Returns the treshold frequency at which words will be ignored
        which do not occur in at least this many docs
    -   [SolrQuery::getMltMinTermFrequency](/class/solrquery.html#SolrQuery::getMltMinTermFrequency)
        — Returns the frequency below which terms will be ignored in the
        source document
    -   [SolrQuery::getMltMinWordLength](/class/solrquery.html#SolrQuery::getMltMinWordLength)
        — Returns the minimum word length below which words will be
        ignored
    -   [SolrQuery::getMltQueryFields](/class/solrquery.html#SolrQuery::getMltQueryFields)
        — Returns the query fields and their boosts
    -   [SolrQuery::getQuery](/class/solrquery.html#SolrQuery::getQuery)
        — Returns the main query
    -   [SolrQuery::getRows](/class/solrquery.html#SolrQuery::getRows) —
        Returns the maximum number of documents
    -   [SolrQuery::getSortFields](/class/solrquery.html#SolrQuery::getSortFields)
        — Returns all the sort fields
    -   [SolrQuery::getStart](/class/solrquery.html#SolrQuery::getStart)
        — Returns the offset in the complete result set
    -   [SolrQuery::getStats](/class/solrquery.html#SolrQuery::getStats)
        — Returns whether or not stats is enabled
    -   [SolrQuery::getStatsFacets](/class/solrquery.html#SolrQuery::getStatsFacets)
        — Returns all the stats facets that were set
    -   [SolrQuery::getStatsFields](/class/solrquery.html#SolrQuery::getStatsFields)
        — Returns all the statistics fields
    -   [SolrQuery::getTerms](/class/solrquery.html#SolrQuery::getTerms)
        — Returns whether or not the TermsComponent is enabled
    -   [SolrQuery::getTermsField](/class/solrquery.html#SolrQuery::getTermsField)
        — Returns the field from which the terms are retrieved
    -   [SolrQuery::getTermsIncludeLowerBound](/class/solrquery.html#SolrQuery::getTermsIncludeLowerBound)
        — Returns whether or not to include the lower bound in the
        result set
    -   [SolrQuery::getTermsIncludeUpperBound](/class/solrquery.html#SolrQuery::getTermsIncludeUpperBound)
        — Returns whether or not to include the upper bound term in the
        result set
    -   [SolrQuery::getTermsLimit](/class/solrquery.html#SolrQuery::getTermsLimit)
        — Returns the maximum number of terms Solr should return
    -   [SolrQuery::getTermsLowerBound](/class/solrquery.html#SolrQuery::getTermsLowerBound)
        — Returns the term to start at
    -   [SolrQuery::getTermsMaxCount](/class/solrquery.html#SolrQuery::getTermsMaxCount)
        — Returns the maximum document frequency
    -   [SolrQuery::getTermsMinCount](/class/solrquery.html#SolrQuery::getTermsMinCount)
        — Returns the minimum document frequency to return in order to
        be included
    -   [SolrQuery::getTermsPrefix](/class/solrquery.html#SolrQuery::getTermsPrefix)
        — Returns the term prefix
    -   [SolrQuery::getTermsReturnRaw](/class/solrquery.html#SolrQuery::getTermsReturnRaw)
        — Whether or not to return raw characters
    -   [SolrQuery::getTermsSort](/class/solrquery.html#SolrQuery::getTermsSort)
        — Returns an integer indicating how terms are sorted
    -   [SolrQuery::getTermsUpperBound](/class/solrquery.html#SolrQuery::getTermsUpperBound)
        — Returns the term to stop at
    -   [SolrQuery::getTimeAllowed](/class/solrquery.html#SolrQuery::getTimeAllowed)
        — Returns the time in milliseconds allowed for the query to
        finish
    -   [SolrQuery::removeExpandFilterQuery](/class/solrquery.html#SolrQuery::removeExpandFilterQuery)
        — Removes an expand filter query
    -   [SolrQuery::removeExpandSortField](/class/solrquery.html#SolrQuery::removeExpandSortField)
        — Removes an expand sort field from the expand.sort parameter
    -   [SolrQuery::removeFacetDateField](/class/solrquery.html#SolrQuery::removeFacetDateField)
        — Removes one of the facet date fields
    -   [SolrQuery::removeFacetDateOther](/class/solrquery.html#SolrQuery::removeFacetDateOther)
        — Removes one of the facet.date.other parameters
    -   [SolrQuery::removeFacetField](/class/solrquery.html#SolrQuery::removeFacetField)
        — Removes one of the facet.date parameters
    -   [SolrQuery::removeFacetQuery](/class/solrquery.html#SolrQuery::removeFacetQuery)
        — Removes one of the facet.query parameters
    -   [SolrQuery::removeField](/class/solrquery.html#SolrQuery::removeField)
        — Removes a field from the list of fields
    -   [SolrQuery::removeFilterQuery](/class/solrquery.html#SolrQuery::removeFilterQuery)
        — Removes a filter query
    -   [SolrQuery::removeHighlightField](/class/solrquery.html#SolrQuery::removeHighlightField)
        — Removes one of the fields used for highlighting
    -   [SolrQuery::removeMltField](/class/solrquery.html#SolrQuery::removeMltField)
        — Removes one of the moreLikeThis fields
    -   [SolrQuery::removeMltQueryField](/class/solrquery.html#SolrQuery::removeMltQueryField)
        — Removes one of the moreLikeThis query fields
    -   [SolrQuery::removeSortField](/class/solrquery.html#SolrQuery::removeSortField)
        — Removes one of the sort fields
    -   [SolrQuery::removeStatsFacet](/class/solrquery.html#SolrQuery::removeStatsFacet)
        — Removes one of the stats.facet parameters
    -   [SolrQuery::removeStatsField](/class/solrquery.html#SolrQuery::removeStatsField)
        — Removes one of the stats.field parameters
    -   [SolrQuery::setEchoHandler](/class/solrquery.html#SolrQuery::setEchoHandler)
        — Toggles the echoHandler parameter
    -   [SolrQuery::setEchoParams](/class/solrquery.html#SolrQuery::setEchoParams)
        — Determines what kind of parameters to include in the response
    -   [SolrQuery::setExpand](/class/solrquery.html#SolrQuery::setExpand)
        — Enables/Disables the Expand Component
    -   [SolrQuery::setExpandQuery](/class/solrquery.html#SolrQuery::setExpandQuery)
        — Sets the expand.q parameter
    -   [SolrQuery::setExpandRows](/class/solrquery.html#SolrQuery::setExpandRows)
        — Sets the number of rows to display in each group
        (expand.rows). Server Default 5
    -   [SolrQuery::setExplainOther](/class/solrquery.html#SolrQuery::setExplainOther)
        — Sets the explainOther common query parameter
    -   [SolrQuery::setFacet](/class/solrquery.html#SolrQuery::setFacet)
        — Maps to the facet parameter. Enables or disables facetting
    -   [SolrQuery::setFacetDateEnd](/class/solrquery.html#SolrQuery::setFacetDateEnd)
        — Maps to facet.date.end
    -   [SolrQuery::setFacetDateGap](/class/solrquery.html#SolrQuery::setFacetDateGap)
        — Maps to facet.date.gap
    -   [SolrQuery::setFacetDateHardEnd](/class/solrquery.html#SolrQuery::setFacetDateHardEnd)
        — Maps to facet.date.hardend
    -   [SolrQuery::setFacetDateStart](/class/solrquery.html#SolrQuery::setFacetDateStart)
        — Maps to facet.date.start
    -   [SolrQuery::setFacetEnumCacheMinDefaultFrequency](/class/solrquery.html#SolrQuery::setFacetEnumCacheMinDefaultFrequency)
        — Sets the minimum document frequency used for determining term
        count
    -   [SolrQuery::setFacetLimit](/class/solrquery.html#SolrQuery::setFacetLimit)
        — Maps to facet.limit
    -   [SolrQuery::setFacetMethod](/class/solrquery.html#SolrQuery::setFacetMethod)
        — Specifies the type of algorithm to use when faceting a field
    -   [SolrQuery::setFacetMinCount](/class/solrquery.html#SolrQuery::setFacetMinCount)
        — Maps to facet.mincount
    -   [SolrQuery::setFacetMissing](/class/solrquery.html#SolrQuery::setFacetMissing)
        — Maps to facet.missing
    -   [SolrQuery::setFacetOffset](/class/solrquery.html#SolrQuery::setFacetOffset)
        — Sets the offset into the list of constraints to allow for
        pagination
    -   [SolrQuery::setFacetPrefix](/class/solrquery.html#SolrQuery::setFacetPrefix)
        — Specifies a string prefix with which to limits the terms on
        which to facet
    -   [SolrQuery::setFacetSort](/class/solrquery.html#SolrQuery::setFacetSort)
        — Determines the ordering of the facet field constraints
    -   [SolrQuery::setGroup](/class/solrquery.html#SolrQuery::setGroup)
        — Enable/Disable result grouping (group parameter)
    -   [SolrQuery::setGroupCachePercent](/class/solrquery.html#SolrQuery::setGroupCachePercent)
        — Enables caching for result grouping
    -   [SolrQuery::setGroupFacet](/class/solrquery.html#SolrQuery::setGroupFacet)
        — Sets group.facet parameter
    -   [SolrQuery::setGroupFormat](/class/solrquery.html#SolrQuery::setGroupFormat)
        — Sets the group format, result structure (group.format
        parameter)
    -   [SolrQuery::setGroupLimit](/class/solrquery.html#SolrQuery::setGroupLimit)
        — Specifies the number of results to return for each group. The
        server default value is 1
    -   [SolrQuery::setGroupMain](/class/solrquery.html#SolrQuery::setGroupMain)
        — If true, the result of the first field grouping command is
        used as the main result list in the response, using
        group.format=simple
    -   [SolrQuery::setGroupNGroups](/class/solrquery.html#SolrQuery::setGroupNGroups)
        — If true, Solr includes the number of groups that have matched
        the query in the results
    -   [SolrQuery::setGroupOffset](/class/solrquery.html#SolrQuery::setGroupOffset)
        — Sets the group.offset parameter
    -   [SolrQuery::setGroupTruncate](/class/solrquery.html#SolrQuery::setGroupTruncate)
        — If true, facet counts are based on the most relevant document
        of each group matching the query
    -   [SolrQuery::setHighlight](/class/solrquery.html#SolrQuery::setHighlight)
        — Enables or disables highlighting
    -   [SolrQuery::setHighlightAlternateField](/class/solrquery.html#SolrQuery::setHighlightAlternateField)
        — Specifies the backup field to use
    -   [SolrQuery::setHighlightFormatter](/class/solrquery.html#SolrQuery::setHighlightFormatter)
        — Specify a formatter for the highlight output
    -   [SolrQuery::setHighlightFragmenter](/class/solrquery.html#SolrQuery::setHighlightFragmenter)
        — Sets a text snippet generator for highlighted text
    -   [SolrQuery::setHighlightFragsize](/class/solrquery.html#SolrQuery::setHighlightFragsize)
        — The size of fragments to consider for highlighting
    -   [SolrQuery::setHighlightHighlightMultiTerm](/class/solrquery.html#SolrQuery::setHighlightHighlightMultiTerm)
        — Use SpanScorer to highlight phrase terms
    -   [SolrQuery::setHighlightMaxAlternateFieldLength](/class/solrquery.html#SolrQuery::setHighlightMaxAlternateFieldLength)
        — Sets the maximum number of characters of the field to return
    -   [SolrQuery::setHighlightMaxAnalyzedChars](/class/solrquery.html#SolrQuery::setHighlightMaxAnalyzedChars)
        — Specifies the number of characters into a document to look for
        suitable snippets
    -   [SolrQuery::setHighlightMergeContiguous](/class/solrquery.html#SolrQuery::setHighlightMergeContiguous)
        — Whether or not to collapse contiguous fragments into a single
        fragment
    -   [SolrQuery::setHighlightRegexMaxAnalyzedChars](/class/solrquery.html#SolrQuery::setHighlightRegexMaxAnalyzedChars)
        — Specify the maximum number of characters to analyze
    -   [SolrQuery::setHighlightRegexPattern](/class/solrquery.html#SolrQuery::setHighlightRegexPattern)
        — Specify the regular expression for fragmenting
    -   [SolrQuery::setHighlightRegexSlop](/class/solrquery.html#SolrQuery::setHighlightRegexSlop)
        — Sets the factor by which the regex fragmenter can stray from
        the ideal fragment size
    -   [SolrQuery::setHighlightRequireFieldMatch](/class/solrquery.html#SolrQuery::setHighlightRequireFieldMatch)
        — Require field matching during highlighting
    -   [SolrQuery::setHighlightSimplePost](/class/solrquery.html#SolrQuery::setHighlightSimplePost)
        — Sets the text which appears after a highlighted term
    -   [SolrQuery::setHighlightSimplePre](/class/solrquery.html#SolrQuery::setHighlightSimplePre)
        — Sets the text which appears before a highlighted term
    -   [SolrQuery::setHighlightSnippets](/class/solrquery.html#SolrQuery::setHighlightSnippets)
        — Sets the maximum number of highlighted snippets to generate
        per field
    -   [SolrQuery::setHighlightUsePhraseHighlighter](/class/solrquery.html#SolrQuery::setHighlightUsePhraseHighlighter)
        — Whether to highlight phrase terms only when they appear within
        the query phrase
    -   [SolrQuery::setMlt](/class/solrquery.html#SolrQuery::setMlt) —
        Enables or disables moreLikeThis
    -   [SolrQuery::setMltBoost](/class/solrquery.html#SolrQuery::setMltBoost)
        — Set if the query will be boosted by the interesting term
        relevance
    -   [SolrQuery::setMltCount](/class/solrquery.html#SolrQuery::setMltCount)
        — Set the number of similar documents to return for each result
    -   [SolrQuery::setMltMaxNumQueryTerms](/class/solrquery.html#SolrQuery::setMltMaxNumQueryTerms)
        — Sets the maximum number of query terms included
    -   [SolrQuery::setMltMaxNumTokens](/class/solrquery.html#SolrQuery::setMltMaxNumTokens)
        — Specifies the maximum number of tokens to parse
    -   [SolrQuery::setMltMaxWordLength](/class/solrquery.html#SolrQuery::setMltMaxWordLength)
        — Sets the maximum word length
    -   [SolrQuery::setMltMinDocFrequency](/class/solrquery.html#SolrQuery::setMltMinDocFrequency)
        — Sets the mltMinDoc frequency
    -   [SolrQuery::setMltMinTermFrequency](/class/solrquery.html#SolrQuery::setMltMinTermFrequency)
        — Sets the frequency below which terms will be ignored in the
        source docs
    -   [SolrQuery::setMltMinWordLength](/class/solrquery.html#SolrQuery::setMltMinWordLength)
        — Sets the minimum word length
    -   [SolrQuery::setOmitHeader](/class/solrquery.html#SolrQuery::setOmitHeader)
        — Exclude the header from the returned results
    -   [SolrQuery::setQuery](/class/solrquery.html#SolrQuery::setQuery)
        — Sets the search query
    -   [SolrQuery::setRows](/class/solrquery.html#SolrQuery::setRows) —
        Specifies the maximum number of rows to return in the result
    -   [SolrQuery::setShowDebugInfo](/class/solrquery.html#SolrQuery::setShowDebugInfo)
        — Flag to show debug information
    -   [SolrQuery::setStart](/class/solrquery.html#SolrQuery::setStart)
        — Specifies the number of rows to skip
    -   [SolrQuery::setStats](/class/solrquery.html#SolrQuery::setStats)
        — Enables or disables the Stats component
    -   [SolrQuery::setTerms](/class/solrquery.html#SolrQuery::setTerms)
        — Enables or disables the TermsComponent
    -   [SolrQuery::setTermsField](/class/solrquery.html#SolrQuery::setTermsField)
        — Sets the name of the field to get the Terms from
    -   [SolrQuery::setTermsIncludeLowerBound](/class/solrquery.html#SolrQuery::setTermsIncludeLowerBound)
        — Include the lower bound term in the result set
    -   [SolrQuery::setTermsIncludeUpperBound](/class/solrquery.html#SolrQuery::setTermsIncludeUpperBound)
        — Include the upper bound term in the result set
    -   [SolrQuery::setTermsLimit](/class/solrquery.html#SolrQuery::setTermsLimit)
        — Sets the maximum number of terms to return
    -   [SolrQuery::setTermsLowerBound](/class/solrquery.html#SolrQuery::setTermsLowerBound)
        — Specifies the Term to start from
    -   [SolrQuery::setTermsMaxCount](/class/solrquery.html#SolrQuery::setTermsMaxCount)
        — Sets the maximum document frequency
    -   [SolrQuery::setTermsMinCount](/class/solrquery.html#SolrQuery::setTermsMinCount)
        — Sets the minimum document frequency
    -   [SolrQuery::setTermsPrefix](/class/solrquery.html#SolrQuery::setTermsPrefix)
        — Restrict matches to terms that start with the prefix
    -   [SolrQuery::setTermsReturnRaw](/class/solrquery.html#SolrQuery::setTermsReturnRaw)
        — Return the raw characters of the indexed term
    -   [SolrQuery::setTermsSort](/class/solrquery.html#SolrQuery::setTermsSort)
        — Specifies how to sort the returned terms
    -   [SolrQuery::setTermsUpperBound](/class/solrquery.html#SolrQuery::setTermsUpperBound)
        — Sets the term to stop at
    -   [SolrQuery::setTimeAllowed](/class/solrquery.html#SolrQuery::setTimeAllowed)
        — The time allowed for search to finish
-   [SolrDisMaxQuery](/class/solrdismaxquery.html) — The SolrDisMaxQuery
    class
    -   [SolrDisMaxQuery::addBigramPhraseField](/class/solrdismaxquery.html#SolrDisMaxQuery::addBigramPhraseField)
        — Adds a Phrase Bigram Field (pf2 parameter)
    -   [SolrDisMaxQuery::addBoostQuery](/class/solrdismaxquery.html#SolrDisMaxQuery::addBoostQuery)
        — Adds a boost query field with value and optional boost (bq
        parameter)
    -   [SolrDisMaxQuery::addPhraseField](/class/solrdismaxquery.html#SolrDisMaxQuery::addPhraseField)
        — Adds a Phrase Field (pf parameter)
    -   [SolrDisMaxQuery::addQueryField](/class/solrdismaxquery.html#SolrDisMaxQuery::addQueryField)
        — Add a query field with optional boost (qf parameter)
    -   [SolrDisMaxQuery::addTrigramPhraseField](/class/solrdismaxquery.html#SolrDisMaxQuery::addTrigramPhraseField)
        — Adds a Trigram Phrase Field (pf3 parameter)
    -   [SolrDisMaxQuery::addUserField](/class/solrdismaxquery.html#SolrDisMaxQuery::addUserField)
        — Adds a field to User Fields Parameter (uf)
    -   [SolrDisMaxQuery::\_\_construct](/class/solrdismaxquery.html#SolrDisMaxQuery::__construct)
        — Class Constructor
    -   [SolrDisMaxQuery::removeBigramPhraseField](/class/solrdismaxquery.html#SolrDisMaxQuery::removeBigramPhraseField)
        — Removes phrase bigram field (pf2 parameter)
    -   [SolrDisMaxQuery::removeBoostQuery](/class/solrdismaxquery.html#SolrDisMaxQuery::removeBoostQuery)
        — Removes a boost query partial by field name (bq)
    -   [SolrDisMaxQuery::removePhraseField](/class/solrdismaxquery.html#SolrDisMaxQuery::removePhraseField)
        — Removes a Phrase Field (pf parameter)
    -   [SolrDisMaxQuery::removeQueryField](/class/solrdismaxquery.html#SolrDisMaxQuery::removeQueryField)
        — Removes a Query Field (qf parameter)
    -   [SolrDisMaxQuery::removeTrigramPhraseField](/class/solrdismaxquery.html#SolrDisMaxQuery::removeTrigramPhraseField)
        — Removes a Trigram Phrase Field (pf3 parameter)
    -   [SolrDisMaxQuery::removeUserField](/class/solrdismaxquery.html#SolrDisMaxQuery::removeUserField)
        — Removes a field from The User Fields Parameter (uf)
    -   [SolrDisMaxQuery::setBigramPhraseFields](/class/solrdismaxquery.html#SolrDisMaxQuery::setBigramPhraseFields)
        — Sets Bigram Phrase Fields and their boosts (and slops) using
        pf2 parameter
    -   [SolrDisMaxQuery::setBigramPhraseSlop](/class/solrdismaxquery.html#SolrDisMaxQuery::setBigramPhraseSlop)
        — Sets Bigram Phrase Slop (ps2 parameter)
    -   [SolrDisMaxQuery::setBoostFunction](/class/solrdismaxquery.html#SolrDisMaxQuery::setBoostFunction)
        — Sets a Boost Function (bf parameter)
    -   [SolrDisMaxQuery::setBoostQuery](/class/solrdismaxquery.html#SolrDisMaxQuery::setBoostQuery)
        — Directly Sets Boost Query Parameter (bq)
    -   [SolrDisMaxQuery::setMinimumMatch](/class/solrdismaxquery.html#SolrDisMaxQuery::setMinimumMatch)
        — Set Minimum "Should" Match (mm)
    -   [SolrDisMaxQuery::setPhraseFields](/class/solrdismaxquery.html#SolrDisMaxQuery::setPhraseFields)
        — Sets Phrase Fields and their boosts (and slops) using pf2
        parameter
    -   [SolrDisMaxQuery::setPhraseSlop](/class/solrdismaxquery.html#SolrDisMaxQuery::setPhraseSlop)
        — Sets the default slop on phrase queries (ps parameter)
    -   [SolrDisMaxQuery::setQueryAlt](/class/solrdismaxquery.html#SolrDisMaxQuery::setQueryAlt)
        — Set Query Alternate (q.alt parameter)
    -   [SolrDisMaxQuery::setQueryPhraseSlop](/class/solrdismaxquery.html#SolrDisMaxQuery::setQueryPhraseSlop)
        — Specifies the amount of slop permitted on phrase queries
        explicitly included in the user's query string (qf parameter)
    -   [SolrDisMaxQuery::setTieBreaker](/class/solrdismaxquery.html#SolrDisMaxQuery::setTieBreaker)
        — Sets Tie Breaker parameter (tie parameter)
    -   [SolrDisMaxQuery::setTrigramPhraseFields](/class/solrdismaxquery.html#SolrDisMaxQuery::setTrigramPhraseFields)
        — Directly Sets Trigram Phrase Fields (pf3 parameter)
    -   [SolrDisMaxQuery::setTrigramPhraseSlop](/class/solrdismaxquery.html#SolrDisMaxQuery::setTrigramPhraseSlop)
        — Sets Trigram Phrase Slop (ps3 parameter)
    -   [SolrDisMaxQuery::setUserFields](/class/solrdismaxquery.html#SolrDisMaxQuery::setUserFields)
        — Sets User Fields parameter (uf)
    -   [SolrDisMaxQuery::useDisMaxQueryParser](/class/solrdismaxquery.html#SolrDisMaxQuery::useDisMaxQueryParser)
        — Switch QueryParser to be DisMax Query Parser
    -   [SolrDisMaxQuery::useEDisMaxQueryParser](/class/solrdismaxquery.html#SolrDisMaxQuery::useEDisMaxQueryParser)
        — Switch QueryParser to be EDisMax
-   [SolrCollapseFunction](/class/solrcollapsefunction.html) — The
    SolrCollapseFunction class
    -   [SolrCollapseFunction::\_\_construct](/class/solrcollapsefunction.html#SolrCollapseFunction::__construct)
        — Constructor
    -   [SolrCollapseFunction::getField](/class/solrcollapsefunction.html#SolrCollapseFunction::getField)
        — Returns the field that is being collapsed on
    -   [SolrCollapseFunction::getHint](/class/solrcollapsefunction.html#SolrCollapseFunction::getHint)
        — Returns collapse hint
    -   [SolrCollapseFunction::getMax](/class/solrcollapsefunction.html#SolrCollapseFunction::getMax)
        — Returns max parameter
    -   [SolrCollapseFunction::getMin](/class/solrcollapsefunction.html#SolrCollapseFunction::getMin)
        — Returns min parameter
    -   [SolrCollapseFunction::getNullPolicy](/class/solrcollapsefunction.html#SolrCollapseFunction::getNullPolicy)
        — Returns null policy
    -   [SolrCollapseFunction::getSize](/class/solrcollapsefunction.html#SolrCollapseFunction::getSize)
        — Returns size parameter
    -   [SolrCollapseFunction::setField](/class/solrcollapsefunction.html#SolrCollapseFunction::setField)
        — Sets the field to collapse on
    -   [SolrCollapseFunction::setHint](/class/solrcollapsefunction.html#SolrCollapseFunction::setHint)
        — Sets collapse hint
    -   [SolrCollapseFunction::setMax](/class/solrcollapsefunction.html#SolrCollapseFunction::setMax)
        — Selects the group heads by the max value of a numeric field or
        function query
    -   [SolrCollapseFunction::setMin](/class/solrcollapsefunction.html#SolrCollapseFunction::setMin)
        — Sets the initial size of the collapse data structures when
        collapsing on a numeric field only
    -   [SolrCollapseFunction::setNullPolicy](/class/solrcollapsefunction.html#SolrCollapseFunction::setNullPolicy)
        — Sets the NULL Policy
    -   [SolrCollapseFunction::setSize](/class/solrcollapsefunction.html#SolrCollapseFunction::setSize)
        — Sets the initial size of the collapse data structures when
        collapsing on a numeric field only
    -   [SolrCollapseFunction::\_\_toString](/class/solrcollapsefunction.html#SolrCollapseFunction::__toString)
        — Returns a string representing the constructed collapse
        function
-   [SolrException](/class/solrexception.html) — The SolrException class
    -   [SolrException::getInternalInfo](/class/solrexception.html#SolrException::getInternalInfo)
        — Returns internal information where the Exception was thrown
-   [SolrClientException](/class/solrclientexception.html) — The
    SolrClientException class
    -   [SolrClientException::getInternalInfo](/class/solrclientexception.html#SolrClientException::getInternalInfo)
        — Returns internal information where the Exception was thrown
-   [SolrServerException](/class/solrserverexception.html) — The
    SolrServerException class
    -   [SolrServerException::getInternalInfo](/class/solrserverexception.html#SolrServerException::getInternalInfo)
        — Returns internal information where the Exception was thrown
-   [SolrIllegalArgumentException](/class/solrillegalargumentexception.html)
    — The SolrIllegalArgumentException class
    -   [SolrIllegalArgumentException::getInternalInfo](/class/solrillegalargumentexception.html#SolrIllegalArgumentException::getInternalInfo)
        — Returns internal information where the Exception was thrown
-   [SolrIllegalOperationException](/class/solrillegaloperationexception.html)
    — The SolrIllegalOperationException class
    -   [SolrIllegalOperationException::getInternalInfo](/class/solrillegaloperationexception.html#SolrIllegalOperationException::getInternalInfo)
        — Returns internal information where the Exception was thrown
-   [SolrMissingMandatoryParameterException](/class/solrmissingmandatoryparameterexception.html)
    — The SolrMissingMandatoryParameterException class

Introduction
------------

Contains utility methods for retrieving the current extension version
and preparing query phrases.

Also contains method for escaping query strings and parsing XML
responses.

Class synopsis
--------------

**SolrUtils**

<span class="ooclass"> <span class="modifier">abstract</span> class
**SolrUtils** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">SolrObject</span>
<span class="methodname">digestXmlResponse</span> ( <span
class="methodparam"><span class="type">string</span>
`$xmlresponse`</span> \[, <span class="methodparam"><span
class="type">int</span> `$parse_mode`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">escapeQueryChars</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getSolrVersion</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">queryPhrase</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

}

SolrUtils::digestXmlResponse
============================

Parses an response XML string into a SolrObject

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">SolrObject</span>
<span class="methodname">SolrUtils::digestXmlResponse</span> ( <span
class="methodparam"><span class="type">string</span>
`$xmlresponse`</span> \[, <span class="methodparam"><span
class="type">int</span> `$parse_mode`<span class="initializer"> =
0</span></span> \] )

This method parses an response XML string from the Apache Solr server
into a SolrObject. It throws a SolrException if there was an error.

### Parameters

`xmlresponse`  
The XML response string from the Solr server.

`parse_mode`  
Use SolrResponse::PARSE\_SOLR\_OBJ or SolrResponse::PARSE\_SOLR\_DOC

### Return Values

Returns the SolrObject representing the XML response.

If the parse\_mode parameter is set to SolrResponse::PARSE\_SOLR\_OBJ
Solr documents will be parses as SolrObject instances.

If it is set to SolrResponse::PARSE\_SOLR\_DOC, they will be parsed as
SolrDocument instances.

SolrUtils::escapeQueryChars
===========================

Escapes a lucene query string

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">SolrUtils::escapeQueryChars</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> )

Lucene supports escaping special characters that are part of the query
syntax.

The current list special characters are:

``` description
+ - && || ! ( ) { } [ ] ^ " ~ * ? : \ /
```

These characters are part of the query syntax and must be escaped

### Parameters

`str`  
This is the query string to be escaped.

### Return Values

Returns the escaped string or **`FALSE`** on failure.

SolrUtils::getSolrVersion
=========================

Returns the current version of the Solr extension

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">SolrUtils::getSolrVersion</span> ( <span
class="methodparam">void</span> )

Returns the current Solr version.

### Parameters

This function has no parameters.

### Return Values

The current version of the Apache Solr extension.

SolrUtils::queryPhrase
======================

Prepares a phrase from an unescaped lucene string

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">SolrUtils::queryPhrase</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> )

Prepares a phrase from an unescaped lucene string.

### Parameters

`str`  
The lucene phrase.

### Return Values

Returns the phrase contained in double quotes.

Introduction
------------

This class represents a Solr document that is about to be submitted to
the Solr index.

Class synopsis
--------------

**SolrInputDocument**

<span class="ooclass"> <span class="modifier">final</span> class
**SolrInputDocument** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrInputDocument::SORT_DEFAULT` <span class="initializer"> = 1</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`SolrInputDocument::SORT_ASC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrInputDocument::SORT_DESC` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrInputDocument::SORT_FIELD_NAME` <span class="initializer"> =
1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrInputDocument::SORT_FIELD_VALUE_COUNT` <span class="initializer"> =
2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrInputDocument::SORT_FIELD_BOOST_VALUE` <span class="initializer"> =
4</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">addChildDocument</span> ( <span
class="methodparam"><span class="type">SolrInputDocument</span>
`$child`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">addChildDocuments</span> ( <span
class="methodparam"><span class="type">array</span> `&$docs`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">string</span>
`$fieldValue`</span> \[, <span class="methodparam"><span
class="type">float</span> `$fieldBoostValue`<span class="initializer"> =
0.0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clear</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">deleteField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">fieldExists</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getBoost</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getChildDocuments</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getChildDocumentsCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">getField</span> ( <span class="methodparam"><span
class="type">string</span> `$fieldName`</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getFieldBoost</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">getFieldCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getFieldNames</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasChildDocuments</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">merge</span> ( <span class="methodparam"><span
class="type">SolrInputDocument</span> `$sourceDoc`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$overwrite`<span
class="initializer"> = **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">reset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setBoost</span> ( <span
class="methodparam"><span class="type">float</span>
`$documentBoostValue`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFieldBoost</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">float</span>
`$fieldBoostValue`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">sort</span> ( <span class="methodparam"><span
class="type">int</span> `$sortOrderBy`</span> \[, <span
class="methodparam"><span class="type">int</span> `$sortDirection`<span
class="initializer"> = SolrInputDocument::SORT\_ASC</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">toArray</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

SolrInputDocument Class Constants
---------------------------------

**`SolrInputDocument::SORT_DEFAULT`**  
Sorts the fields in ascending order.

**`SolrInputDocument::SORT_ASC`**  
Sorts the fields in ascending order.

**`SolrInputDocument::SORT_DESC`**  
Sorts the fields in descending order.

**`SolrInputDocument::SORT_FIELD_NAME`**  
Sorts the fields by name

**`SolrInputDocument::SORT_FIELD_VALUE_COUNT`**  
Sorts the fields by number of values.

**`SolrInputDocument::SORT_FIELD_BOOST_VALUE`**  
Sorts the fields by boost value.

SolrInputDocument::addChildDocument
===================================

Adds a child document for block indexing

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrInputDocument::addChildDocument</span> (
<span class="methodparam"><span class="type">SolrInputDocument</span>
`$child`</span> )

Adds a child document to construct a document block with nested
documents.

### Parameters

`child`  
A <span class="type">SolrInputDocument</span> object.

### Errors/Exceptions

Throws <span class="classname">SolrIllegalArgumentException</span> on
failure.

Throws <span class="classname">SolrException</span> on internal failure.

### Return Values

### Examples

**Example \#1 <span
class="function">SolrInputDocument::addChildDocument</span> example**

``` php
<?php

include "bootstrap.php";

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
    'path'     => SOLR_SERVER_STORE_PATH,
);

$client = new SolrClient($options);

$product = new SolrInputDocument();

$product->addField('id', 'P-BLACK');
$product->addField('cat', 'tshirt');
$product->addField('cat', 'polo');
$product->addField('content_type', 'product');

$small = new SolrInputDocument();
$small->addField('id', 'TS-BLK-S');
$small->addField('content_type', 'sku');
$small->addField('size', 'S');
$small->addField('inventory', 100);

$medium = new SolrInputDocument();
$medium->addField('id', 'TS-BLK-M');
$medium->addField('content_type', 'sku');
$medium->addField('size', 'M');
$medium->addField('inventory', 200);

$large = new SolrInputDocument();
$large->addField('id', 'TS-BLK-L');
$large->addField('content_type', 'sku');
$large->addField('size', 'L');
$large->addField('inventory', 300);

// add child documents 
$product->addChildDocument($small);
$product->addChildDocument($medium);
$product->addChildDocument($large);

// add product document block to the index
$updateResponse = $client->addDocument(
        $product,
        true, // overwrite if the document exists
        10000 // commit within 10 seconds
);

print_r($updateResponse->getResponse());
```

The above example will output something similar to:

    SolrObject Object
    (
        [responseHeader] => SolrObject Object
            (
                [status] => 0
                [QTime] => 5
            )
    )

### See Also

-   <span class="methodname">SolrInputDocument::addChildDocuments</span>
-   <span class="methodname">SolrInputDocument::hasChildDocuments</span>
-   <span class="methodname">SolrInputDocument::getChildDocuments</span>
-   <span
    class="methodname">SolrInputDocument::getChildDocumentsCount</span>

SolrInputDocument::addChildDocuments
====================================

Adds an array of child documents

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrInputDocument::addChildDocuments</span> (
<span class="methodparam"><span class="type">array</span>
`&$docs`</span> )

Adds an array of child documents to the current input document.

### Parameters

`docs`  
An <span class="type">array</span> of <span
class="type">SolrInputDocument</span> objects.

### Errors/Exceptions

Throws <span class="classname">SolrIllegalArgumentException</span> on
failure.

Throws <span class="classname">SolrException</span> on internal failure.

### Return Values

### Examples

**Example \#1 <span
class="function">SolrInputDocument::addChildDocuments</span> example**

``` php
<?php

include "bootstrap.php";

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
    'path'     => SOLR_SERVER_STORE_PATH,
);

$client = new SolrClient($options);

$product = new SolrInputDocument();

$product->addField('id', 'P-BLACK');
$product->addField('cat', 'tshirt');
$product->addField('cat', 'polo');
$product->addField('content_type', 'product');

$small = new SolrInputDocument();
$small->addField('id', 'TS-BLK-S');
$small->addField('content_type', 'sku');
$small->addField('size', 'S');
$small->addField('inventory', 100);

$medium = new SolrInputDocument();
$medium->addField('id', 'TS-BLK-M');
$medium->addField('content_type', 'sku');
$medium->addField('size', 'M');
$medium->addField('inventory', 200);

$large = new SolrInputDocument();
$large->addField('id', 'TS-BLK-L');
$large->addField('content_type', 'sku');
$large->addField('size', 'L');
$large->addField('inventory', 300);

// add child documents 
$skus = [$small, $medium, $large];
$product->addChildDocuments($skus);

// add the product document block to the index
$updateResponse = $client->addDocument(
        $product,
        true, // overwrite if the document exists
        10000 // commit within 10 seconds
);

print_r($updateResponse->getResponse());
```

The above example will output something similar to:

    SolrObject Object
    (
        [responseHeader] => SolrObject Object
            (
                [status] => 0
                [QTime] => 5
            )
    )

### See Also

-   <span class="methodname">SolrInputDocument::addChildDocument</span>
-   <span class="methodname">SolrInputDocument::hasChildDocuments</span>
-   <span class="methodname">SolrInputDocument::getChildDocuments</span>
-   <span
    class="methodname">SolrInputDocument::getChildDocumentsCount</span>

SolrInputDocument::addField
===========================

Adds a field to the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::addField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">string</span>
`$fieldValue`</span> \[, <span class="methodparam"><span
class="type">float</span> `$fieldBoostValue`<span class="initializer"> =
0.0</span></span> \] )

For multi-value fields, if a valid boost value is specified, the
specified value will be multiplied by the current boost value for this
field.

### Parameters

`fieldName`  
The name of the field

`fieldValue`  
The value for the field.

`fieldBoostValue`  
The index time boost for the field. Though this cannot be negative, you
can still pass values less than 1.0 but they must be greater than zero.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrInputDocument::clear
========================

Resets the input document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::clear</span> ( <span
class="methodparam">void</span> )

Resets the document by dropping all the fields and resets the document
boost to zero.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrInputDocument::\_\_clone
============================

Creates a copy of a SolrDocument

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrInputDocument::\_\_clone</span> ( <span
class="methodparam">void</span> )

Should not be called directly. It is used to create a deep copy of a
SolrInputDocument.

### Parameters

This function has no parameters.

### Return Values

Creates a new SolrInputDocument instance.

SolrInputDocument::\_\_construct
================================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrInputDocument::\_\_construct</span> ( <span
class="methodparam">void</span> )

Constructor.

### Parameters

This function has no parameters.

### Return Values

None.

SolrInputDocument::deleteField
==============================

Removes a field from the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::deleteField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Removes a field from the document.

### Parameters

`fieldName`  
The name of the field.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrInputDocument::\_\_destruct
===============================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrInputDocument::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Destructor

### Parameters

This function has no parameters.

### Return Values

None.

SolrInputDocument::fieldExists
==============================

Checks if a field exists

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::fieldExists</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Checks if a field exists

### Parameters

`fieldName`  
Name of the field.

### Return Values

Returns **`TRUE`** if the field was found and **`FALSE`** if it was not
found.

SolrInputDocument::getBoost
===========================

Retrieves the current boost value for the document

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">SolrInputDocument::getBoost</span> ( <span
class="methodparam">void</span> )

Retrieves the current boost value for the document.

### Parameters

This function has no parameters.

### Return Values

Returns the boost value on success and **`FALSE`** on failure.

SolrInputDocument::getChildDocuments
====================================

Returns an array of child documents (SolrInputDocument)

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrInputDocument::getChildDocuments</span> (
<span class="methodparam">void</span> )

Returns an array of child documents (SolrInputDocument)

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrInputDocument::addChildDocument</span>
-   <span class="methodname">SolrInputDocument::addChildDocuments</span>
-   <span class="methodname">SolrInputDocument::hasChildDocuments</span>
-   <span
    class="methodname">SolrInputDocument::getChildDocumentsCount</span>

SolrInputDocument::getChildDocumentsCount
=========================================

Returns the number of child documents

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrInputDocument::getChildDocumentsCount</span> (
<span class="methodparam">void</span> )

Returns the number of child documents

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrInputDocument::addChildDocument</span>
-   <span class="methodname">SolrInputDocument::addChildDocuments</span>
-   <span class="methodname">SolrInputDocument::hasChildDocuments</span>
-   <span class="methodname">SolrInputDocument::getChildDocuments</span>

SolrInputDocument::getField
===========================

Retrieves a field by name

### Description

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">SolrInputDocument::getField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Retrieves a field in the document.

### Parameters

`fieldName`  
The name of the field.

### Return Values

Returns a SolrDocumentField object on success and **`FALSE`** on
failure.

SolrInputDocument::getFieldBoost
================================

Retrieves the boost value for a particular field

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">SolrInputDocument::getFieldBoost</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Retrieves the boost value for a particular field.

### Parameters

`fieldName`  
The name of the field.

### Return Values

Returns the boost value for the field or **`FALSE`** if there was an
error.

SolrInputDocument::getFieldCount
================================

Returns the number of fields in the document

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">SolrInputDocument::getFieldCount</span> ( <span
class="methodparam">void</span> )

Returns the number of fields in the document.

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success or **`FALSE`** on failure.

SolrInputDocument::getFieldNames
================================

Returns an array containing all the fields in the document

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrInputDocument::getFieldNames</span> ( <span
class="methodparam">void</span> )

Returns an array containing all the fields in the document.

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`FALSE`** on failure.

SolrInputDocument::hasChildDocuments
====================================

Returns true if the document has any child documents

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::hasChildDocuments</span> (
<span class="methodparam">void</span> )

Checks whether the document has any child documents

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrInputDocument::addChildDocument</span>
-   <span class="methodname">SolrInputDocument::addChildDocuments</span>
-   <span class="methodname">SolrInputDocument::getChildDocuments</span>
-   <span
    class="methodname">SolrInputDocument::getChildDocumentsCount</span>

SolrInputDocument::merge
========================

Merges one input document into another

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::merge</span> ( <span
class="methodparam"><span class="type">SolrInputDocument</span>
`$sourceDoc`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$overwrite`<span class="initializer"> =
**`TRUE`**</span></span> \] )

Merges one input document into another.

### Parameters

`sourceDoc`  
The source document.

`overwrite`  
If this is **`TRUE`** it will replace matching fields in the destination
document.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. In the future,
this will be modified to return the number of fields in the new
document.

SolrInputDocument::reset
========================

This is an alias of SolrInputDocument::clear

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::reset</span> ( <span
class="methodparam">void</span> )

This is an alias of SolrInputDocument::clear

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrInputDocument::setBoost
===========================

Sets the boost value for this document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::setBoost</span> ( <span
class="methodparam"><span class="type">float</span>
`$documentBoostValue`</span> )

Sets the boost value for this document.

### Parameters

`documentBoostValue`  
The index-time boost value for this document.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrInputDocument::setFieldBoost
================================

Sets the index-time boost value for a field

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::setFieldBoost</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">float</span>
`$fieldBoostValue`</span> )

Sets the index-time boost value for a field. This replaces the current
boost value for this field.

### Parameters

`fieldName`  
The name of the field.

`fieldBoostValue`  
The index time boost value.

SolrInputDocument::sort
=======================

Sorts the fields within the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrInputDocument::sort</span> ( <span
class="methodparam"><span class="type">int</span> `$sortOrderBy`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$sortDirection`<span class="initializer"> =
SolrInputDocument::SORT\_ASC</span></span> \] )

``` description
The fields are rearranged according to the specified criteria and sort direction
   
   Fields can be sorted by boost values, field names and number of values.
   
   The $order_by parameter must be one of :
   
   * SolrInputDocument::SORT_FIELD_NAME
   * SolrInputDocument::SORT_FIELD_BOOST_VALUE
   * SolrInputDocument::SORT_FIELD_VALUE_COUNT
   
   The sort direction can be one of :
   
   * SolrInputDocument::SORT_DEFAULT
   * SolrInputDocument::SORT_ASC
   * SolrInputDocument::SORT_DESC
```

### Parameters

`sortOrderBy`  
The sort criteria

`sortDirection`  
The sort direction

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrInputDocument::toArray
==========================

Returns an array representation of the input document

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrInputDocument::toArray</span> ( <span
class="methodparam">void</span> )

Returns an array representation of the input document.

### Parameters

This function has no parameters.

### Return Values

Returns an array containing the fields. It returns **`FALSE`** on
failure.

Introduction
------------

Represents a Solr document retrieved from a query response.

Class synopsis
--------------

**SolrDocument**

<span class="ooclass"> <span class="modifier">final</span> class
**SolrDocument** </span> <span class="oointerface">implements <span
class="interfacename">ArrayAccess</span> </span> <span
class="oointerface">, <span class="interfacename">Iterator</span>
</span> <span class="oointerface">, <span
class="interfacename">Serializable</span> </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrDocument::SORT_DEFAULT` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrDocument::SORT_ASC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrDocument::SORT_DESC` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrDocument::SORT_FIELD_NAME` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrDocument::SORT_FIELD_VALUE_COUNT` <span class="initializer"> =
2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrDocument::SORT_FIELD_BOOST_VALUE` <span class="initializer"> =
4</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">string</span>
`$fieldValue`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clear</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">deleteField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">fieldExists</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">\_\_get</span> ( <span class="methodparam"><span
class="type">string</span> `$fieldName`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getChildDocuments</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getChildDocumentsCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">getField</span> ( <span class="methodparam"><span
class="type">string</span> `$fieldName`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFieldCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getFieldNames</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrInputDocument</span> <span
class="methodname">getInputDocument</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasChildDocuments</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">merge</span> ( <span class="methodparam"><span
class="type">SolrDocument</span> `$sourceDoc`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$overwrite`<span
class="initializer"> = **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">offsetGet</span> ( <span class="methodparam"><span
class="type">string</span> `$fieldName`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">string</span>
`$fieldValue`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">reset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">string</span>
`$fieldValue`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">sort</span> ( <span class="methodparam"><span
class="type">int</span> `$sortOrderBy`</span> \[, <span
class="methodparam"><span class="type">int</span> `$sortDirection`<span
class="initializer"> = SolrDocument::SORT\_ASC</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">toArray</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">\_\_unset</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`SolrDocument::SORT_DEFAULT`**  
Default mode for sorting fields within the document.

**`SolrDocument::SORT_ASC`**  
Sorts the fields in ascending order

**`SolrDocument::SORT_DESC`**  
Sorts the fields in descending order

**`SolrDocument::SORT_FIELD_NAME`**  
Sorts the fields by field name.

**`SolrDocument::SORT_FIELD_VALUE_COUNT`**  
Sorts the fields by number of values in each field.

**`SolrDocument::SORT_FIELD_BOOST_VALUE`**  
Sorts the fields by thier boost values.

SolrDocument::addField
======================

Adds a field to the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::addField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">string</span>
`$fieldValue`</span> )

This method adds a field to the SolrDocument instance.

### Parameters

`fieldName`  
The name of the field

`fieldValue`  
The value of the field.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::clear
===================

Drops all the fields in the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::clear</span> ( <span
class="methodparam">void</span> )

Resets the current object. Discards all the fields and resets the
document boost to zero.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::\_\_clone
=======================

Creates a copy of a SolrDocument object

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrDocument::\_\_clone</span> ( <span
class="methodparam">void</span> )

Creates a copy of a SolrDocument object. Not to be called directly.

### Parameters

This function has no parameters.

### Return Values

None.

SolrDocument::\_\_construct
===========================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrDocument::\_\_construct</span> ( <span
class="methodparam">void</span> )

Constructor for SolrDocument

### Parameters

This function has no parameters.

### Return Values

SolrDocument::current
=====================

Retrieves the current field

### Description

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">SolrDocument::current</span> ( <span
class="methodparam">void</span> )

Retrieves the current field

### Parameters

This function has no parameters.

### Return Values

Returns the field

SolrDocument::deleteField
=========================

Removes a field from the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::deleteField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Removes a field from the document.

### Parameters

`fieldName`  
Name of the field

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::\_\_destruct
==========================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrDocument::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Destructor for SolrDocument.

### Parameters

This function has no parameters.

### Return Values

SolrDocument::fieldExists
=========================

Checks if a field exists in the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::fieldExists</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Checks if the requested field as a valid fieldname in the document.

### Parameters

`fieldName`  
The name of the field.

### Return Values

Returns **`TRUE`** if the field is present and **`FALSE`** if it does
not.

SolrDocument::\_\_get
=====================

Access the field as a property

### Description

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">SolrDocument::\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Magic method for accessing the field as a property.

### Parameters

`fieldName`  
The name of the field.

### Return Values

Returns a SolrDocumentField instance.

SolrDocument::getChildDocuments
===============================

Returns an array of child documents (SolrDocument)

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrDocument::getChildDocuments</span> ( <span
class="methodparam">void</span> )

Returns an array of child documents (SolrDocument)

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrDocument::hasChildDocuments</span>
-   <span class="methodname">SolrDocument::getChildDocumentsCount</span>

SolrDocument::getChildDocumentsCount
====================================

Returns the number of child documents

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrDocument::getChildDocumentsCount</span> ( <span
class="methodparam">void</span> )

Returns the number of child documents

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrDocument::hasChildDocuments</span>
-   <span class="methodname">SolrDocument::getChildDocuments</span>

SolrDocument::getField
======================

Retrieves a field by name

### Description

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">SolrDocument::getField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Retrieves a field by name.

### Parameters

`fieldName`  
Name of the field.

### Return Values

Returns a SolrDocumentField on success and **`FALSE`** on failure.

SolrDocument::getFieldCount
===========================

Returns the number of fields in this document

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrDocument::getFieldCount</span> ( <span
class="methodparam">void</span> )

Returns the number of fields in this document. Multi-value fields are
only counted once.

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`FALSE`** on failure.

SolrDocument::getFieldNames
===========================

Returns an array of fields names in the document

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrDocument::getFieldNames</span> ( <span
class="methodparam">void</span> )

Returns an array of fields names in the document.

### Parameters

This function has no parameters.

### Return Values

Returns an array containing the names of the fields in this document.

SolrDocument::getInputDocument
==============================

Returns a SolrInputDocument equivalent of the object

### Description

<span class="modifier">public</span> <span
class="type">SolrInputDocument</span> <span
class="methodname">SolrDocument::getInputDocument</span> ( <span
class="methodparam">void</span> )

Returns a SolrInputDocument equivalent of the object. This is useful if
one wishes to resubmit/update a document retrieved from a query.

### Parameters

This function has no parameters.

### Return Values

Returns a SolrInputDocument on success and **`NULL`** on failure.

SolrDocument::hasChildDocuments
===============================

Checks whether the document has any child documents

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::hasChildDocuments</span> ( <span
class="methodparam">void</span> )

Checks whether the document has any child documents

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrDocument::getChildDocuments</span>
-   <span class="methodname">SolrDocument::getChildDocumentsCount</span>

SolrDocument::\_\_isset
=======================

Checks if a field exists

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Checks if a field exists

### Parameters

`fieldName`  
Name of the field.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::key
=================

Retrieves the current key

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrDocument::key</span> ( <span
class="methodparam">void</span> )

Retrieves the current key.

### Parameters

This function has no parameters.

### Return Values

Returns the current key.

SolrDocument::merge
===================

Merges source to the current SolrDocument

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::merge</span> ( <span
class="methodparam"><span class="type">SolrDocument</span>
`$sourceDoc`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$overwrite`<span class="initializer"> =
**`TRUE`**</span></span> \] )

Merges source to the current SolrDocument.

### Parameters

`sourceDoc`  
The source document.

`overwrite`  
If this is **`TRUE`** then fields with the same name in the destination
document will be overwritten.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::next
==================

Moves the internal pointer to the next field

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrDocument::next</span> ( <span
class="methodparam">void</span> )

Moves the internal pointer to the next field.

### Parameters

This function has no parameters.

### Return Values

This method has no return value.

SolrDocument::offsetExists
==========================

Checks if a particular field exists

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::offsetExists</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Checks if a particular field exists. This is used when the object is
treated as an array.

### Parameters

`fieldName`  
The name of the field.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::offsetGet
=======================

Retrieves a field

### Description

<span class="modifier">public</span> <span
class="type">SolrDocumentField</span> <span
class="methodname">SolrDocument::offsetGet</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

This is used to retrieve the field when the object is treated as an
array.

### Parameters

`fieldName`  
The name of the field.

### Return Values

Returns a SolrDocumentField object.

SolrDocument::offsetSet
=======================

Adds a field to the document

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrDocument::offsetSet</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">string</span>
`$fieldValue`</span> )

Used when the object is treated as an array to add a field to the
document.

### Parameters

`fieldName`  
The name of the field.

`fieldValue`  
The value for this field.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::offsetUnset
=========================

Removes a field

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrDocument::offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Removes a field from the document.

### Parameters

`fieldName`  
The name of the field.

### Return Values

No return value.

SolrDocument::reset
===================

This is an alias to SolrDocument::clear()

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::reset</span> ( <span
class="methodparam">void</span> )

This is an alias to SolrDocument::clear()

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::rewind
====================

Resets the internal pointer to the beginning

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrDocument::rewind</span> ( <span
class="methodparam">void</span> )

Resets the internal pointer to the beginning.

### Parameters

This function has no parameters.

### Return Values

This method has no return value.

SolrDocument::serialize
=======================

Used for custom serialization

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrDocument::serialize</span> ( <span
class="methodparam">void</span> )

Used for custom serialization.

### Parameters

This function has no parameters.

### Return Values

Returns a string representing the serialized Solr document.

SolrDocument::\_\_set
=====================

Adds another field to the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
, <span class="methodparam"><span class="type">string</span>
`$fieldValue`</span> )

Adds another field to the document. Used to set the fields as new
properties.

### Parameters

`fieldName`  
Name of the field.

`fieldValue`  
Field value.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::sort
==================

Sorts the fields in the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::sort</span> ( <span
class="methodparam"><span class="type">int</span> `$sortOrderBy`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$sortDirection`<span class="initializer"> =
SolrDocument::SORT\_ASC</span></span> \] )

``` description
The fields are rearranged according to the specified criteria and sort direction
   
   Fields can be sorted by boost values, field names and number of values.
   
   The sortOrderBy parameter must be one of :
   
   * SolrDocument::SORT_FIELD_NAME
   * SolrDocument::SORT_FIELD_BOOST_VALUE
   * SolrDocument::SORT_FIELD_VALUE_COUNT
   
   The sortDirection can be one of :
   
   * SolrDocument::SORT_DEFAULT
   * SolrDocument::SORT_ASC
   * SolrDocument::SORT_DESC
   
   The default way is to sort in ascending order.
```

### Parameters

`sortOrderBy`  
The sort criteria.

`sortDirection`  
The sort direction.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::toArray
=====================

Returns an array representation of the document

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrDocument::toArray</span> ( <span
class="methodparam">void</span> )

Returns an array representation of the document.

### Parameters

This function has no parameters.

### Return Values

Returns an array representation of the document.

### Examples

**Example \#1 <span class="methodname">SolrDocument::toArray</span>
example**

``` php
<?php

$doc = new SolrDocument();

$doc->addField('id', 1123);

$doc->features = "PHP Client Side";
$doc->features = "Fast development cycles";

$doc['cat'] = 'Software';
$doc['cat'] = 'Custom Search';
$doc->cat   = 'Information Technology';

print_r($doc->toArray());

?>
```

The above example will output something similar to:

    Array
    (
        [document_boost] => 0
        [field_count] => 3
        [fields] => Array
            (
                [0] => SolrDocumentField Object
                    (
                        [name] => id
                        [boost] => 0
                        [values] => Array
                            (
                                [0] => 1123
                            )

                    )

                [1] => SolrDocumentField Object
                    (
                        [name] => features
                        [boost] => 0
                        [values] => Array
                            (
                                [0] => PHP Client Side
                                [1] => Fast development cycles
                            )

                    )

                [2] => SolrDocumentField Object
                    (
                        [name] => cat
                        [boost] => 0
                        [values] => Array
                            (
                                [0] => Software
                                [1] => Custom Search
                                [2] => Information Technology
                            )

                    )

            )

    )

SolrDocument::unserialize
=========================

Custom serialization of SolrDocument objects

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrDocument::unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

Custom serialization of SolrDocument objects

### Parameters

`serialized`  
An XML representation of the document.

### Return Values

None.

SolrDocument::\_\_unset
=======================

Removes a field from the document

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::\_\_unset</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

Removes a field from the document when the field is access as an object
property.

### Parameters

`fieldName`  
The name of the field.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrDocument::valid
===================

Checks if the current position internally is still valid

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrDocument::valid</span> ( <span
class="methodparam">void</span> )

Checks if the current position internally is still valid. It is used
during foreach operations.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success and **`FALSE`** if the current position is
no longer valid.

Introduction
------------

This represents a field in a Solr document. All its properties are
read-only.

Class synopsis
--------------

**SolrDocumentField**

<span class="ooclass"> <span class="modifier">final</span> class
**SolrDocumentField** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">string</span>
`$name` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">float</span>
`$boost` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">array</span>
`$values` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`name`  
The name of the field.

`boost`  
The boost value for the field

`values`  
An array of values for this field

SolrDocumentField::\_\_construct
================================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrDocumentField::\_\_construct</span> ( <span
class="methodparam">void</span> )

Constructor.

### Parameters

This function has no parameters.

### Return Values

None.

SolrDocumentField::\_\_destruct
===============================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrDocumentField::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Destructor.

### Parameters

This function has no parameters.

### Return Values

None.

Introduction
------------

This is an object whose properties can also by accessed using the array
syntax. All its properties are read-only.

Class synopsis
--------------

**SolrObject**

<span class="ooclass"> <span class="modifier">final</span> class
**SolrObject** </span> <span class="oointerface">implements <span
class="interfacename">ArrayAccess</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getPropertyNames</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">string</span>
`$property_name`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">offsetGet</span> ( <span
class="methodparam"><span class="type">string</span>
`$property_name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">string</span>
`$property_name`</span> , <span class="methodparam"><span
class="type">string</span> `$property_value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span>
`$property_name`</span> )

}

SolrObject::\_\_construct
=========================

Creates Solr object

### Description

<span class="modifier">public</span> <span
class="methodname">SolrObject::\_\_construct</span> ( <span
class="methodparam">void</span> )

Creates Solr object.

### Parameters

This function has no parameters.

### Return Values

None

### Examples

**Example \#1 <span class="methodname">SolrObject::\_\_construct</span>
example**

``` php
<?php
/* ... */
?>
```

The above example will output something similar to:

    ...

### See Also

-   <span class="methodname">Classname::Method</span>

SolrObject::\_\_destruct
========================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrObject::\_\_destruct</span> ( <span
class="methodparam">void</span> )

The destructor

### Parameters

This function has no parameters.

### Return Values

None.

SolrObject::getPropertyNames
============================

Returns an array of all the names of the properties

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrObject::getPropertyNames</span> ( <span
class="methodparam">void</span> )

Returns an array of all the names of the properties

### Parameters

This function has no parameters.

### Return Values

Returns an array.

SolrObject::offsetExists
========================

Checks if the property exists

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrObject::offsetExists</span> ( <span
class="methodparam"><span class="type">string</span>
`$property_name`</span> )

Checks if the property exists. This is used when the object is treated
as an array.

### Parameters

`property_name`  
The name of the property.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrObject::offsetGet
=====================

Used to retrieve a property

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SolrObject::offsetGet</span> ( <span
class="methodparam"><span class="type">string</span>
`$property_name`</span> )

Used to get the value of a property. This is used when the object is
treated as an array.

### Parameters

`property_name`  
Name of the property.

### Return Values

Returns the property value.

SolrObject::offsetSet
=====================

Sets the value for a property

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrObject::offsetSet</span> ( <span
class="methodparam"><span class="type">string</span>
`$property_name`</span> , <span class="methodparam"><span
class="type">string</span> `$property_value`</span> )

Sets the value for a property. This is used when the object is treated
as an array. This object is read-only. This should never be attempted.

### Parameters

`property_name`  
The name of the property.

`property_value`  
The new value.

### Return Values

None.

SolrObject::offsetUnset
=======================

Unsets the value for the property

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrObject::offsetUnset</span> ( <span
class="methodparam"><span class="type">string</span>
`$property_name`</span> )

Unsets the value for the property. This is used when the object is
treated as an array. This object is read-only. This should never be
attempted.

### Parameters

`property_name`  
The name of the property.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="methodname">SolrObject::offsetUnset</span>
example**

``` php
<?php
/* ... */
?>
```

The above example will output something similar to:

    ...

### See Also

-   <span class="methodname">Classname::Method</span>

Introduction
------------

Used to send requests to a Solr server. Currently, cloning and
serialization of SolrClient instances is not supported.

Class synopsis
--------------

**SolrClient**

<span class="ooclass"> <span class="modifier">final</span> class
**SolrClient** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrClient::SEARCH_SERVLET_TYPE` <span class="initializer"> = 1</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`SolrClient::UPDATE_SERVLET_TYPE` <span class="initializer"> = 2</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`SolrClient::THREADS_SERVLET_TYPE` <span class="initializer"> = 4</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`SolrClient::PING_SERVLET_TYPE` <span class="initializer"> = 8</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrClient::TERMS_SERVLET_TYPE` <span class="initializer"> = 16</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`SolrClient::SYSTEM_SERVLET_TYPE` <span class="initializer"> = 32</span>
;

<span class="modifier">const</span> <span class="type">string</span>
`SolrClient::DEFAULT_SEARCH_SERVLET` <span class="initializer"> =
select</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`SolrClient::DEFAULT_UPDATE_SERVLET` <span class="initializer"> =
update</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`SolrClient::DEFAULT_THREADS_SERVLET` <span class="initializer"> =
admin/threads</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`SolrClient::DEFAULT_PING_SERVLET` <span class="initializer"> =
admin/ping</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`SolrClient::DEFAULT_TERMS_SERVLET` <span class="initializer"> =
terms</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`SolrClient::DEFAULT_SYSTEM_SERVLET` <span class="initializer"> =
admin/system</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">addDocument</span> ( <span class="methodparam"><span
class="type">SolrInputDocument</span> `$doc`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$overwrite`<span
class="initializer"> = **`TRUE`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$commitWithin`<span
class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">addDocuments</span> ( <span
class="methodparam"><span class="type">array</span> `$docs`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$overwrite`<span class="initializer"> = **`TRUE`**</span></span> \[,
<span class="methodparam"><span class="type">int</span>
`$commitWithin`<span class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">commit</span> (\[ <span class="methodparam"><span
class="type">bool</span> `$softCommit`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$waitSearcher`<span class="initializer"> =
**`TRUE`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$expungeDeletes`<span class="initializer"> =
**`FALSE`**</span></span> \]\]\] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">array</span>
`$clientOptions`</span> )

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">deleteById</span> ( <span class="methodparam"><span
class="type">string</span> `$id`</span> )

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">deleteByIds</span> ( <span class="methodparam"><span
class="type">array</span> `$ids`</span> )

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">deleteByQueries</span> ( <span
class="methodparam"><span class="type">array</span> `$queries`</span> )

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">deleteByQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrQueryResponse</span> <span
class="methodname">getById</span> ( <span class="methodparam"><span
class="type">string</span> `$id`</span> )

<span class="modifier">public</span> <span
class="type">SolrQueryResponse</span> <span
class="methodname">getByIds</span> ( <span class="methodparam"><span
class="type">array</span> `$ids`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDebug</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getOptions</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">optimize</span> (\[ <span class="methodparam"><span
class="type">int</span> `$maxSegments`<span class="initializer"> =
1</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$softCommit`<span class="initializer"> =
**`TRUE`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$waitSearcher`<span class="initializer"> =
**`TRUE`**</span></span> \]\]\] )

<span class="modifier">public</span> <span
class="type">SolrPingResponse</span> <span
class="methodname">ping</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrQueryResponse</span> <span
class="methodname">query</span> ( <span class="methodparam"><span
class="type">SolrParams</span> `$query`</span> )

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">request</span> ( <span class="methodparam"><span
class="type">string</span> `$raw_request`</span> )

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">rollback</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setResponseWriter</span> ( <span
class="methodparam"><span class="type">string</span>
`$responseWriter`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setServlet</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">system</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">threads</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`SolrClient::SEARCH_SERVLET_TYPE`**  
Used when updating the search servlet.

**`SolrClient::UPDATE_SERVLET_TYPE`**  
Used when updating the update servlet.

**`SolrClient::THREADS_SERVLET_TYPE`**  
Used when updating the threads servlet.

**`SolrClient::PING_SERVLET_TYPE`**  
Used when updating the ping servlet.

**`SolrClient::TERMS_SERVLET_TYPE`**  
Used when updating the terms servlet.

**`SolrClient::SYSTEM_SERVLET_TYPE`**  
Used when retrieving system information from the system servlet.

**`SolrClient::DEFAULT_SEARCH_SERVLET`**  
This is the initial value for the search servlet.

**`SolrClient::DEFAULT_UPDATE_SERVLET`**  
This is the initial value for the update servlet.

**`SolrClient::DEFAULT_THREADS_SERVLET`**  
This is the initial value for the threads servlet.

**`SolrClient::DEFAULT_PING_SERVLET`**  
This is the initial value for the ping servlet.

**`SolrClient::DEFAULT_TERMS_SERVLET`**  
This is the initial value for the terms servlet used for the
TermsComponent

**`SolrClient::DEFAULT_SYSTEM_SERVLET`**  
This is the initial value for the system servlet used to obtain Solr
Server information

SolrClient::addDocument
=======================

Adds a document to the index

### Description

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">SolrClient::addDocument</span> ( <span
class="methodparam"><span class="type">SolrInputDocument</span>
`$doc`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$overwrite`<span class="initializer"> =
**`TRUE`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$commitWithin`<span class="initializer"> =
0</span></span> \]\] )

This method adds a document to the index.

### Parameters

`doc`  
The SolrInputDocument instance.

`overwrite`  
Whether to overwrite existing document or not. If **`FALSE`** there will
be duplicates (several documents with the same ID).

**Warning**
PECL Solr \< 2.0 $allowDups was used instead of $overwrite, which does
the same functionality with exact opposite bool flag.

$allowDups = false is the same as $overwrite = true

`commitWithin`  
Number of milliseconds within which to auto commit this document.
Available since Solr 1.4 . Default (0) means disabled.

When this value specified, it leaves the control of when to do the
commit to Solr itself, optimizing number of commits to a minimum while
still fulfilling the update latency requirements, and Solr will
automatically do a commit when the oldest add in the buffer is due.

### Return Values

Returns a <span class="type">SolrUpdateResponse</span> object or throws
an Exception on failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to process the request.

### Examples

**Example \#1 <span class="methodname">SolrClient::addDocument</span>
example**

``` php
<?php

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
);

$client = new SolrClient($options);

$doc = new SolrInputDocument();

$doc->addField('id', 334455);
$doc->addField('cat', 'Software');
$doc->addField('cat', 'Lucene');

$updateResponse = $client->addDocument($doc);

// you will have to commit changes to be written if you didn't use $commitWithin
$client->commit();

print_r($updateResponse->getResponse());

?>
```

The above example will output something similar to:


    SolrObject Object
    (
        [responseHeader] => SolrObject Object
            (
                [status] => 0
                [QTime] => 1
            )

    )

**Example \#2 <span class="methodname">SolrClient::addDocument</span>
example 2**

``` php
<?php

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
);

$client = new SolrClient($options);

$doc = new SolrInputDocument();

$doc->addField('id', 334455);
$doc->addField('cat', 'Software');
$doc->addField('cat', 'Lucene');

// No need to call commit() because $commitWithin is passed, so Solr Server will auto commit within 10 seconds
$updateResponse = $client->addDocument($doc, false, 10000);

print_r($updateResponse->getResponse());

?>
```

The above example will output something similar to:


    SolrObject Object
    (
        [responseHeader] => SolrObject Object
            (
                [status] => 0
                [QTime] => 1
            )

    )

### See Also

-   <span class="methodname">SolrClient::addDocuments</span>
-   <span class="methodname">SolrClient::commit</span>

SolrClient::addDocuments
========================

Adds a collection of SolrInputDocument instances to the index

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrClient::addDocuments</span> ( <span
class="methodparam"><span class="type">array</span> `$docs`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$overwrite`<span class="initializer"> = **`TRUE`**</span></span> \[,
<span class="methodparam"><span class="type">int</span>
`$commitWithin`<span class="initializer"> = 0</span></span> \]\] )

Adds a collection of documents to the index.

### Parameters

`docs`  
An array containing the collection of SolrInputDocument instances. This
array must be an actual variable.

`overwrite`  
Whether to overwrite existing documents or not. If **`FALSE`** there
will be duplicates (several documents with the same ID).

**Warning**
PECL Solr \< 2.0 $allowDups was used instead of $overwrite, which does
the same functionality with exact opposite bool flag.

$allowDups = false is the same as $overwrite = true

`commitWithin`  
Number of milliseconds within which to auto commit this document.
Available since Solr 1.4 . Default (0) means disabled.

When this value specified, it leaves the control of when to do the
commit to Solr itself, optimizing number of commits to a minimum while
still fulfilling the update latency requirements, and Solr will
automatically do a commit when the oldest add in the buffer is due.

### Return Values

Returns a <span class="type">SolrUpdateResponse</span> object or throws
an exception on failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to process the request.

### Examples

**Example \#1 <span class="methodname">SolrClient::addDocuments</span>
example**

``` php
<?php

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
);

$client = new SolrClient($options);

$doc = new SolrInputDocument();

$doc->addField('id', 334455);
$doc->addField('cat', 'Software');
$doc->addField('cat', 'Lucene');

$doc2 = clone $doc;

$doc2->deleteField('id');
$doc2->addField('id', 334456);

$docs = array($doc, $doc2);

$updateResponse = $client->addDocuments($docs);

// no changes will be written to disk unless $commitWithin is passed or SolrClient::commit is called

print_r($updateResponse->getResponse());

?>
```

The above example will output something similar to:

    SolrObject Object
    (
        [responseHeader] => SolrObject Object
            (
                [status] => 0
                [QTime] => 2
            )

    )

### See Also

-   <span class="methodname">SolrClient::addDocument</span>
-   <span class="methodname">SolrClient::commit</span>

SolrClient::commit
==================

Finalizes all add/deletes made to the index

### Description

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">SolrClient::commit</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$softCommit`<span
class="initializer"> = **`FALSE`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$waitSearcher`<span
class="initializer"> = **`TRUE`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$expungeDeletes`<span class="initializer"> = **`FALSE`**</span></span>
\]\]\] )

This method finalizes all add/deletes made to the index.

### Parameters

`softCommit`  
This will refresh the 'view' of the index in a more performant manner,
but without "on-disk" guarantees. (Solr4.0+)

A soft commit is much faster since it only makes index changes visible
and does not fsync index files or write a new index descriptor. If the
JVM crashes or there is a loss of power, changes that occurred after the
last hard commit will be lost. Search collections that have
near-real-time requirements (that want index changes to be quickly
visible to searches) will want to soft commit often but hard commit less
frequently.

`waitSearcher`  
block until a new searcher is opened and registered as the main query
searcher, making the changes visible.

`expungeDeletes`  
Merge segments with deletes away. (Solr1.4+)

### Return Values

Returns a <span class="classname">SolrUpdateResponse</span> object on
success or throws an exception on failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to process the request.

### Changelog

| Version                | Description                                                                                                                                                                          |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL solr 1.1.0, 2.0.0 | $maxSegments removed                                                                                                                                                                 |
| PECL solr 2.0.0b       | API Changed: SolrClient::commit (\[ int $maxSegments = 0 \[, bool $softCommit = false \[, bool $waitSearcher = true\[, bool $expungeDeletes = false \]\]\] )                         |
| PECL solr 0.9.2        | Signature: SolrClient::commit (\[ int $maxSegments = 1 \[, bool $waitFlush = true \[, bool $waitSearcher = true \]\]\] ). $waitFlush: Block until index changes are flushed to disk. |

### Notes

**Warning**

PECL Solr \>= 2.0 only supports Solr Server \>= 4.0

### See Also

-   <span class="methodname">SolrClient::optimize</span>
-   <span class="methodname">SolrClient::rollback</span>

SolrClient::\_\_construct
=========================

Constructor for the SolrClient object

### Description

<span class="modifier">public</span> <span
class="methodname">SolrClient::\_\_construct</span> ( <span
class="methodparam"><span class="type">array</span>
`$clientOptions`</span> )

Constructor for the SolrClient object

### Parameters

`clientOptions`  
This is an array containing one of the following keys :

``` parameters
- secure          (Boolean value indicating whether or not to connect in secure mode)
 - hostname        (The hostname for the Solr server)
 - port            (The port number)
 - path            (The path to solr)
 - wt              (The name of the response writer e.g. xml, json)
 - login           (The username used for HTTP Authentication, if any)
 - password        (The HTTP Authentication password)
 - proxy_host      (The hostname for the proxy server, if any)
 - proxy_port      (The proxy port)
 - proxy_login     (The proxy username)
 - proxy_password  (The proxy password)
 - timeout         (This is maximum time in seconds allowed for the http data transfer operation. Default is 30 seconds)
 - ssl_cert        (File name to a PEM-formatted file containing the private key + private certificate (concatenated in that order) )
 - ssl_key         (File name to a PEM-formatted private key file only)
 - ssl_keypassword (Password for private key)
 - ssl_cainfo      (Name of file holding one or more CA certificates to verify peer with)
 - ssl_capath      (Name of directory holding multiple CA certificates to verify peer with )
 
 Please note the if the ssl_cert file only contains the private certificate, you have to specify a separate ssl_key file
 
 The ssl_keypassword option is required if the ssl_cert or ssl_key options are set.
```

### Errors/Exceptions

Throws <span class="classname">SolrIllegalArgumentException</span> on
failure.

### Examples

**Example \#1 <span class="methodname">SolrClient::\_\_construct</span>
example**

``` php
<?php

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
    'path'     => SOLR_PATH_TO_SOLR,
    'wt'       => 'xml',
);

$client = new SolrClient($options);

$doc = new SolrInputDocument();

$doc->addField('id', 334455);
$doc->addField('cat', 'Software');
$doc->addField('cat', 'Lucene');

$updateResponse = $client->addDocument($doc);

?>
```

The above example will output something similar to:

### See Also

-   <span class="methodname">SolrClient::getOptions</span>

SolrClient::deleteById
======================

Delete by Id

### Description

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">SolrClient::deleteById</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> )

Deletes the document with the specified ID. Where ID is the value of the
uniqueKey field declared in the schema

### Parameters

`id`  
The value of the uniqueKey field declared in the schema

### Return Values

Returns a <span class="type">SolrUpdateResponse</span> on success and
throws an exception on failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to process the request.

### See Also

-   <span class="methodname">SolrClient::deleteByIds</span>
-   <span class="methodname">SolrClient::deleteByQuery</span>
-   <span class="methodname">SolrClient::deleteByQueries</span>

SolrClient::deleteByIds
=======================

Deletes by Ids

### Description

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">SolrClient::deleteByIds</span> ( <span
class="methodparam"><span class="type">array</span> `$ids`</span> )

Deletes a collection of documents with the specified set of ids.

### Parameters

`ids`  
An array of IDs representing the uniqueKey field declared in the schema
for each document to be deleted. This must be an actual php variable.

### Return Values

Returns a <span class="type">SolrUpdateResponse</span> on success and
throws an exception on failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to process the request.

### See Also

-   <span class="methodname">SolrClient::deleteById</span>
-   <span class="methodname">SolrClient::deleteByQuery</span>
-   <span class="methodname">SolrClient::deleteByQueries</span>

SolrClient::deleteByQueries
===========================

Removes all documents matching any of the queries

### Description

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">SolrClient::deleteByQueries</span> ( <span
class="methodparam"><span class="type">array</span> `$queries`</span> )

Removes all documents matching any of the queries

### Parameters

`queries`  
The array of queries. This must be an actual php variable.

### Return Values

Returns a SolrUpdateResponse on success and throws a SolrClientException
on failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to process the request.

### See Also

-   <span class="methodname">SolrClient::deleteById</span>
-   <span class="methodname">SolrClient::deleteByIds</span>
-   <span class="methodname">SolrClient::deleteByQuery</span>

SolrClient::deleteByQuery
=========================

Deletes all documents matching the given query

### Description

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">SolrClient::deleteByQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

Deletes all documents matching the given query.

### Parameters

`query`  
The query

### Return Values

Returns a <span class="type">SolrUpdateResponse</span> on success and
throws an exception on failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to process the request.

### Examples

**Example \#1 <span class="methodname">SolrQuery::deleteByQuery</span>
example**

``` php
<?php

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
);

$client = new SolrClient($options);

//This will erase the entire index
$client->deleteByQuery("*:*");
$client->commit();

?>
```

### See Also

-   <span class="methodname">SolrClient::deleteById</span>
-   <span class="methodname">SolrClient::deleteByIds</span>
-   <span class="methodname">SolrClient::deleteByQueries</span>

SolrClient::\_\_destruct
========================

Destructor for SolrClient

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrClient::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Destructor

### Parameters

This function has no parameters.

### Return Values

Destructor for SolrClient

### See Also

-   <span class="methodname">SolrClient::\_\_construct</span>

SolrClient::getById
===================

Get Document By Id. Utilizes Solr Realtime Get (RTG)

### Description

<span class="modifier">public</span> <span
class="type">SolrQueryResponse</span> <span
class="methodname">SolrClient::getById</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> )

Get Document By Id. Utilizes Solr Realtime Get (RTG).

### Parameters

`id`  
Document ID

### Return Values

<span class="type">SolrQueryResponse</span>

### Examples

**Example \#1 <span class="function">SolrClient::getById</span>
example**

``` php
<?php

include "bootstrap.php";

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
    'path'     => SOLR_SERVER_PATH
);

$client = new SolrClient($options);
$response = $client->getById('GB18030TEST');
print_r($response->getResponse());

?>
```

The above example will output something similar to:

    SolrObject Object
    (
        [doc] => SolrObject Object
            (
                [id] => GB18030TEST
                [name] => Array
                    (
                        [0] => Test with some GB18030 encoded characters
                    )

                [features] => Array
                    (
                        [0] => No accents here
                        [1] => 这是一个功能
                        [2] => This is a feature (translated)
                        [3] => 这份文件是很有光泽
                        [4] => This document is very shiny (translated)
                    )

                [price] => Array
                    (
                        [0] => 0
                    )

                [inStock] => Array
                    (
                        [0] => 1
                    )

                [_version_] => 1510294336239042560
            )

    )

### See Also

-   <span class="methodname">SolrClient::getByIds</span>

SolrClient::getByIds
====================

Get Documents by their Ids. Utilizes Solr Realtime Get (RTG)

### Description

<span class="modifier">public</span> <span
class="type">SolrQueryResponse</span> <span
class="methodname">SolrClient::getByIds</span> ( <span
class="methodparam"><span class="type">array</span> `$ids`</span> )

Get Documents by their Ids. Utilizes Solr Realtime Get (RTG).

### Parameters

`ids`  
Document ids

### Return Values

<span class="type">SolrQueryResponse</span>

### Examples

**Example \#1 <span class="function">SolrClient::getByIds</span>
example**

``` php
<?php

include "bootstrap.php";

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
    'path'     => SOLR_SERVER_PATH
);

$client = new SolrClient($options);
$response = $client->getByIds(['GB18030TEST', '6H500F0']);

print_r($response->getResponse());

?>
```

The above example will output something similar to:

    SolrObject Object
    (
        [response] => SolrObject Object
            (
                [numFound] => 2
                [start] => 0
                [docs] => Array
                    (
                        [0] => SolrObject Object
                            (
                                [id] => GB18030TEST
                                [name] => Array
                                    (
                                        [0] => Test with some GB18030 encoded characters
                                    )

                                [features] => Array
                                    (
                                        [0] => No accents here
                                        [1] => 这是一个功能
                                        [2] => This is a feature (translated)
                                        [3] => 这份文件是很有光泽
                                        [4] => This document is very shiny (translated)
                                    )

                                [price] => Array
                                    (
                                        [0] => 0
                                    )

                                [inStock] => Array
                                    (
                                        [0] => 1
                                    )

                                [_version_] => 1510294336239042560
                            )

                        [1] => SolrObject Object
                            (
                                [id] => 6H500F0
                                [name] => Array
                                    (
                                        [0] => Maxtor DiamondMax 11 - hard drive - 500 GB - SATA-300
                                    )

                                [manu] => Array
                                    (
                                        [0] => Maxtor Corp.
                                    )

                                [manu_id_s] => maxtor
                                [cat] => Array
                                    (
                                        [0] => electronics
                                        [1] => hard drive
                                    )

                                [features] => Array
                                    (
                                        [0] => SATA 3.0Gb/s, NCQ
                                        [1] => 8.5ms seek
                                        [2] => 16MB cache
                                    )

                                [price] => Array
                                    (
                                        [0] => 350
                                    )

                                [popularity] => Array
                                    (
                                        [0] => 6
                                    )

                                [inStock] => Array
                                    (
                                        [0] => 1
                                    )

                                [store] => Array
                                    (
                                        [0] => 45.17614,-93.87341
                                    )

                                [manufacturedate_dt] => 2006-02-13T15:26:37Z
                                [_version_] => 1510294336449806336
                            )

                    )

            )

    )

### See Also

-   <span class="methodname">SolrClient::getById</span>

SolrClient::getDebug
====================

Returns the debug data for the last connection attempt

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrClient::getDebug</span> ( <span
class="methodparam">void</span> )

Returns the debug data for the last connection attempt

### Parameters

This function has no parameters.

### Return Values

Returns a string on success and null if there is nothing to return.

SolrClient::getOptions
======================

Returns the client options set internally

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrClient::getOptions</span> ( <span
class="methodparam">void</span> )

Returns the client options set internally. Very useful for debugging.
The values returned are readonly and can only be set when the object is
instantiated.

### Parameters

This function has no parameters.

### Return Values

Returns an array containing all the options for the SolrClient object
set internally.

### See Also

-   <span class="methodname">SolrClient::\_\_construct</span>

SolrClient::optimize
====================

Defragments the index

### Description

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">SolrClient::optimize</span> (\[ <span
class="methodparam"><span class="type">int</span> `$maxSegments`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$softCommit`<span
class="initializer"> = **`TRUE`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$waitSearcher`<span
class="initializer"> = **`TRUE`**</span></span> \]\]\] )

Defragments the index for faster search performance.

### Parameters

`maxSegments`  
Optimizes down to at most this number of segments. Since Solr 1.3

`softCommit`  
This will refresh the 'view' of the index in a more performant manner,
but without "on-disk" guarantees. (Solr4.0+)

`waitSearcher`  
Block until a new searcher is opened and registered as the main query
searcher, making the changes visible.

### Return Values

Returns a SolrUpdateResponse on success or throws an exception on
failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to process the request.

### Notes

**Warning**

PECL Solr \>= 2.0 only supports Solr Server \>= 4.0

Prior to PECL Solr 2.0 this method used to accept these arguments "int
$maxSegments, bool $waitFlush, bool $waitSearcher".

### See Also

-   <span class="methodname">SolrClient::commit</span>
-   <span class="methodname">SolrClient::rollback</span>

SolrClient::ping
================

Checks if Solr server is still up

### Description

<span class="modifier">public</span> <span
class="type">SolrPingResponse</span> <span
class="methodname">SolrClient::ping</span> ( <span
class="methodparam">void</span> )

Checks if the Solr server is still alive. Sends a HEAD request to the
Apache Solr server.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="type">SolrPingResponse</span> object on success
and throws an exception on failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to satisfy the request.

### Examples

**Example \#1 <span class="methodname">SolrClient::ping</span> example**

``` php
<?php
$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
);

$client = new SolrClient($options);

$pingresponse = $client->ping();

?>
```

The above example will output something similar to:

SolrClient::query
=================

Sends a query to the server

### Description

<span class="modifier">public</span> <span
class="type">SolrQueryResponse</span> <span
class="methodname">SolrClient::query</span> ( <span
class="methodparam"><span class="type">SolrParams</span> `$query`</span>
)

Sends a query to the server.

### Parameters

`query`  
A <span class="type">SolrParams</span> object. It is recommended to use
<span class="type">SolrQuery</span> for advanced queries.

### Return Values

Returns a <span class="type">SolrQueryResponse</span> object on success
and throws an exception on failure.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to satisfy the query.

### Examples

**Example \#1 <span class="methodname">SolrClient::query</span>
example**

``` php
<?php

$options = array
(
    'hostname' => 'localhost',
    'login'    => 'username',
    'password' => 'password',
    'port'     => '8983',
);

$client = new SolrClient($options);

$query = new SolrQuery();

$query->setQuery('lucene');

$query->setStart(0);

$query->setRows(50);

$query->addField('cat')->addField('features')->addField('id')->addField('timestamp');

$query_response = $client->query($query);

$response = $query_response->getResponse();

print_r($response);

?>
```

The above example will output something similar to:

    SolrObject Object
    (
        [responseHeader] => SolrObject Object
            (
                [status] => 0
                [QTime] => 3
                [params] => SolrObject Object
                    (
                        [fl] => cat,features,id,timestamp
                        [indent] => on
                        [start] => 0
                        [q] => lucene
                        [wt] => xml
                        [version] => 2.2
                        [rows] => 50
                    )

            )

        [response] => SolrObject Object
            (
                [numFound] => 1
                [start] => 0
                [docs] => Array
                    (
                        [0] => SolrObject Object
                            (
                                [id] => SOLR1000
                                [cat] => Array
                                    (
                                        [0] => software
                                        [1] => search
                                    )

                                [features] => Array
                                    (
                                        [0] => Advanced Full-Text Search Capabilities using Lucene
                                        [1] => Optimized for High Volume Web Traffic
                                        [2] => Standards Based Open Interfaces - XML and HTTP
                                        [3] => Comprehensive HTML Administration Interfaces
                                        [4] => Scalability - Efficient Replication to other Solr Search Servers
                                        [5] => Flexible and Adaptable with XML configuration and Schema
                                        [6] => Good unicode support: héllo (hello with an accent over the e)
                                    )

                            )

                    )

            )

    )

SolrClient::request
===================

Sends a raw update request

### Description

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">SolrClient::request</span> ( <span
class="methodparam"><span class="type">string</span>
`$raw_request`</span> )

Sends a raw XML update request to the server

### Parameters

`raw_request`  
An XML string with the raw request to the server.

### Return Values

Returns a <span class="type">SolrUpdateResponse</span> on success.
Throws an exception on failure.

### Errors/Exceptions

Throws <span class="classname">SolrIllegalArgumentException</span> if
`raw_request` was an empty string

Throws <span class="classname">SolrClientException</span> if the client
had failed, or there was a connection issue.

Throws <span class="classname">SolrServerException</span> if the Solr
Server had failed to satisfy the query.

### Examples

**Example \#1 <span class="methodname">SolrClient::request</span>
example**

``` php
<?php
$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
);

$client = new SolrClient($options);

$update_response = $client->request("<commit/>");

$response = $update_response->getResponse();

print_r($response);
?>
```

The above example will output something similar to:

    ...

SolrClient::rollback
====================

Rollbacks all add/deletes made to the index since the last commit

### Description

<span class="modifier">public</span> <span
class="type">SolrUpdateResponse</span> <span
class="methodname">SolrClient::rollback</span> ( <span
class="methodparam">void</span> )

Rollbacks all add/deletes made to the index since the last commit. It
neither calls any event listeners nor creates a new searcher.

### Parameters

This function has no parameters.

### Return Values

Returns a SolrUpdateResponse on success or throws a SolrClientException
on failure.

### See Also

-   <span class="methodname">SolrClient::commit</span>
-   <span class="methodname">SolrClient::optimize</span>

SolrClient::setResponseWriter
=============================

Sets the response writer used to prepare the response from Solr

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrClient::setResponseWriter</span> ( <span
class="methodparam"><span class="type">string</span>
`$responseWriter`</span> )

Sets the response writer used to prepare the response from Solr

### Parameters

`responseWriter`  
One of the following:

-   *json*
-   *phps*
-   *xml*

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="methodname">SolrClient::setResponseWriter</span> example**

``` php
<?php

// This is my custom class for objects
class SolrClass
{
   public $_properties = array();

   public function __get($property_name) {
      
      if (property_exists($this, $property_name)) {
      
          return $this->$property_name;
      
      } else if (isset($_properties[$property_name])) {
      
          return $_properties[$property_name];
      }
      
      return null;
   }
}

$options = array
(
  'hostname' => 'localhost',
  'port' => 8983,
  'path' => '/solr/core1'
);

$client = new SolrClient($options);

$client->setResponseWriter("json");

//$response = $client->ping();

$query = new SolrQuery();

$query->setQuery("*:*");

$query->set("objectClassName", "SolrClass");

$query->set("objectPropertiesStorageMode", 1); // 0 for independent properties, 1 for combined

try
{

$response = $client->query($query);

$resp = $response->getResponse();

print_r($response);

print_r($resp);

} catch (Exception $e) {

print_r($e);

}

?>
```

SolrClient::setServlet
======================

Changes the specified servlet type to a new value

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrClient::setServlet</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Changes the specified servlet type to a new value

### Parameters

`type`  
One of the following :

``` parameters
- SolrClient::SEARCH_SERVLET_TYPE
 - SolrClient::UPDATE_SERVLET_TYPE
 - SolrClient::THREADS_SERVLET_TYPE
 - SolrClient::PING_SERVLET_TYPE
 - SolrClient::TERMS_SERVLET_TYPE
```

`value`  
The new value for the servlet

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrClient::system
==================

Retrieve Solr Server information

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrClient::system</span> ( <span
class="methodparam">void</span> )

Retrieve Solr Server information

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="type">SolrGenericResponse</span> object on
success.

### Errors/Exceptions

Emits <span class="classname">SolrClientException</span> if the client
failed, or there was a connection issue.

Emits <span class="classname">SolrServerException</span> if the Solr
Server failed to satisfy the query.

SolrClient::threads
===================

Checks the threads status

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrClient::threads</span> ( <span
class="methodparam">void</span> )

Checks the threads status

### Parameters

This function has no parameters.

### Return Values

Returns a SolrGenericResponse object.

### Errors/Exceptions

Throws <span class="classname">SolrClientException</span> if the client
failed, or there was a connection issue.

throws <span class="classname">SolrServerException</span> if the Solr
Server failed to process the request.

Introduction
------------

Represents a response from the Solr server.

Class synopsis
--------------

**SolrResponse**

<span class="ooclass"> <span class="modifier">abstract</span> class
**SolrResponse** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrResponse::PARSE_SOLR_OBJ` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrResponse::PARSE_SOLR_DOC` <span class="initializer"> = 1</span> ;

/\* Properties \*/

<span class="modifier">protected</span> <span class="type">int</span>
`$http_status` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$parser_mode` ;

<span class="modifier">protected</span> <span class="type">bool</span>
`$success` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_status_message` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_request_url` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_request_headers` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_request` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_response_headers` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_response` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_digested_response` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDigestedResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getHttpStatus</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getHttpStatusMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getRawRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getRawRequestHeaders</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getRawResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getRawResponseHeaders</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getRequestUrl</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrObject</span> <span
class="methodname">getResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setParseMode</span> (\[ <span
class="methodparam"><span class="type">int</span> `$parser_mode`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">success</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`http_status`  
The http status of the response.

`parser_mode`  
Whether to parse the solr documents as SolrObject or SolrDocument
instances.

`success`  
Was there an error during the request

`http_status_message`  
Detailed message on http status

`http_request_url`  
The request URL

`http_raw_request_headers`  
A string of raw headers sent during the request.

`http_raw_request`  
The raw request sent to the server

`http_raw_response_headers`  
Response headers from the Solr server.

`http_raw_response`  
The response message from the server.

`http_digested_response`  
The response in PHP serialized format.

Predefined Constants
--------------------

SolrResponse Class Constants
----------------------------

**`SolrResponse::PARSE_SOLR_OBJ`**  
Documents should be parsed as SolrObject instances

**`SolrResponse::PARSE_SOLR_DOC`**  
Documents should be parsed as SolrDocument instances.

SolrResponse::getDigestedResponse
=================================

Returns the XML response as serialized PHP data

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getDigestedResponse</span> (
<span class="methodparam">void</span> )

Returns the XML response as serialized PHP data

### Parameters

This function has no parameters.

### Return Values

Returns the XML response as serialized PHP data

SolrResponse::getHttpStatus
===========================

Returns the HTTP status of the response

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrResponse::getHttpStatus</span> ( <span
class="methodparam">void</span> )

Returns the HTTP status of the response.

### Parameters

This function has no parameters.

### Return Values

Returns the HTTP status of the response.

SolrResponse::getHttpStatusMessage
==================================

Returns more details on the HTTP status

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getHttpStatusMessage</span> (
<span class="methodparam">void</span> )

Returns more details on the HTTP status.

### Parameters

This function has no parameters.

### Return Values

Returns more details on the HTTP status

SolrResponse::getRawRequest
===========================

Returns the raw request sent to the Solr server

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequest</span> ( <span
class="methodparam">void</span> )

Returns the raw request sent to the Solr server.

### Parameters

This function has no parameters.

### Return Values

Returns the raw request sent to the Solr server

SolrResponse::getRawRequestHeaders
==================================

Returns the raw request headers sent to the Solr server

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequestHeaders</span> (
<span class="methodparam">void</span> )

Returns the raw request headers sent to the Solr server.

### Parameters

This function has no parameters.

### Return Values

Returns the raw request headers sent to the Solr server

SolrResponse::getRawResponse
============================

Returns the raw response from the server

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponse</span> ( <span
class="methodparam">void</span> )

Returns the raw response from the server.

### Parameters

This function has no parameters.

### Return Values

Returns the raw response from the server.

SolrResponse::getRawResponseHeaders
===================================

Returns the raw response headers from the server

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponseHeaders</span> (
<span class="methodparam">void</span> )

Returns the raw response headers from the server.

### Parameters

This function has no parameters.

### Return Values

Returns the raw response headers from the server.

SolrResponse::getRequestUrl
===========================

Returns the full URL the request was sent to

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRequestUrl</span> ( <span
class="methodparam">void</span> )

Returns the full URL the request was sent to.

### Parameters

This function has no parameters.

### Return Values

Returns the full URL the request was sent to

SolrResponse::getResponse
=========================

Returns a SolrObject representing the XML response from the server

### Description

<span class="modifier">public</span> <span
class="type">SolrObject</span> <span
class="methodname">SolrResponse::getResponse</span> ( <span
class="methodparam">void</span> )

Returns a SolrObject representing the XML response from the server.

### Parameters

This function has no parameters.

### Return Values

Returns a SolrObject representing the XML response from the server

SolrResponse::setParseMode
==========================

Sets the parse mode

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::setParseMode</span> (\[ <span
class="methodparam"><span class="type">int</span> `$parser_mode`<span
class="initializer"> = 0</span></span> \] )

Sets the parse mode.

### Parameters

`parser_mode`  
SolrResponse::PARSE\_SOLR\_DOC parses documents in SolrDocument
instances. SolrResponse::PARSE\_SOLR\_OBJ parses document into
SolrObjects.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SolrResponse::success
=====================

Was the request a success

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::success</span> ( <span
class="methodparam">void</span> )

Used to check if the request to the server was successful.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if it was successful and **`FALSE`** if it was not.

Introduction
------------

Represents a response to a query request.

Class synopsis
--------------

**SolrQueryResponse**

<span class="ooclass"> <span class="modifier">final</span> class
**SolrQueryResponse** </span> <span class="ooclass"> <span
class="modifier">extends</span> **SolrResponse** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrQueryResponse::PARSE_SOLR_OBJ` <span class="initializer"> =
0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQueryResponse::PARSE_SOLR_DOC` <span class="initializer"> =
1</span> ;

/\* Inherited properties \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrResponse::PARSE_SOLR_OBJ` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrResponse::PARSE_SOLR_DOC` <span class="initializer"> = 1</span> ;

<span class="modifier">protected</span> <span class="type">int</span>
`$http_status` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$parser_mode` ;

<span class="modifier">protected</span> <span class="type">bool</span>
`$success` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_status_message` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_request_url` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_request_headers` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_request` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_response_headers` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_response` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_digested_response` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getDigestedResponse</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrResponse::getHttpStatus</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getHttpStatusMessage</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequestHeaders</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponseHeaders</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRequestUrl</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrObject</span> <span
class="methodname">SolrResponse::getResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::setParseMode</span> (\[ <span
class="methodparam"><span class="type">int</span> `$parser_mode`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::success</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

SolrQueryResponse Class constants
---------------------------------

**`SolrQueryResponse::PARSE_SOLR_OBJ`**  
Documents should be parsed as SolrObject instances

**`SolrQueryResponse::PARSE_SOLR_DOC`**  
Documents should be parsed as SolrDocument instances.

SolrQueryResponse::\_\_construct
================================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrQueryResponse::\_\_construct</span> ( <span
class="methodparam">void</span> )

Constructor

### Parameters

This function has no parameters.

### Return Values

None

SolrQueryResponse::\_\_destruct
===============================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrQueryResponse::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Destructor.

### Parameters

This function has no parameters.

### Return Values

None

Introduction
------------

Represents a response to an update request.

Class synopsis
--------------

**SolrUpdateResponse**

<span class="ooclass"> <span class="modifier">final</span> class
**SolrUpdateResponse** </span> <span class="ooclass"> <span
class="modifier">extends</span> **SolrResponse** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrUpdateResponse::PARSE_SOLR_OBJ` <span class="initializer"> =
0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrUpdateResponse::PARSE_SOLR_DOC` <span class="initializer"> =
1</span> ;

/\* Inherited properties \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrResponse::PARSE_SOLR_OBJ` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrResponse::PARSE_SOLR_DOC` <span class="initializer"> = 1</span> ;

<span class="modifier">protected</span> <span class="type">int</span>
`$http_status` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$parser_mode` ;

<span class="modifier">protected</span> <span class="type">bool</span>
`$success` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_status_message` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_request_url` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_request_headers` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_request` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_response_headers` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_response` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_digested_response` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getDigestedResponse</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrResponse::getHttpStatus</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getHttpStatusMessage</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequestHeaders</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponseHeaders</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRequestUrl</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrObject</span> <span
class="methodname">SolrResponse::getResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::setParseMode</span> (\[ <span
class="methodparam"><span class="type">int</span> `$parser_mode`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::success</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

SolrUpdateResponse Class Constants
----------------------------------

**`SolrUpdateResponse::PARSE_SOLR_OBJ`**  
Documents should be parsed as SolrObject instances

**`SolrUpdateResponse::PARSE_SOLR_DOC`**  
Documents should be parsed as SolrDocument instances.

SolrUpdateResponse::\_\_construct
=================================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrUpdateResponse::\_\_construct</span> ( <span
class="methodparam">void</span> )

Constructor

### Parameters

This function has no parameters.

### Return Values

None

SolrUpdateResponse::\_\_destruct
================================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrUpdateResponse::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Destructor

### Parameters

This function has no parameters.

### Return Values

None

Introduction
------------

Represents a response to a ping request to the server

Class synopsis
--------------

**SolrPingResponse**

<span class="ooclass"> <span class="modifier">final</span> class
**SolrPingResponse** </span> <span class="ooclass"> <span
class="modifier">extends</span> **SolrResponse** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrPingResponse::PARSE_SOLR_OBJ` <span class="initializer"> = 0</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`SolrPingResponse::PARSE_SOLR_DOC` <span class="initializer"> = 1</span>
;

/\* Properties \*/

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getResponse</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getDigestedResponse</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrResponse::getHttpStatus</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getHttpStatusMessage</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequestHeaders</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponseHeaders</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRequestUrl</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrObject</span> <span
class="methodname">SolrResponse::getResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::setParseMode</span> (\[ <span
class="methodparam"><span class="type">int</span> `$parser_mode`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::success</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`http_status`  
The http status of the response.

`parser_mode`  
Whether to parse the solr documents as SolrObject or SolrDocument
instances.

`success`  
Was there an error during the request

`http_status_message`  
Detailed message on http status

`http_request_url`  
The request URL

`http_raw_request_headers`  
A string of raw headers sent during the request

`http_raw_request`  
The raw request sent to the server

`http_raw_response_headers`  
Response headers from the Solr server

`http_raw_response`  
The response message from the server

`http_digested_response`  
The response in PHP serialized format.

Predefined Constants
--------------------

SolrPingResponse Class Constants
--------------------------------

**`SolrPingResponse::PARSE_SOLR_OBJ`**  
Documents should be parsed as SolrObject instances

**`SolrPingResponse::PARSE_SOLR_DOC`**  
Documents should be parsed as SolrDocument instances.

SolrPingResponse::\_\_construct
===============================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrPingResponse::\_\_construct</span> ( <span
class="methodparam">void</span> )

Constructor

### Parameters

This function has no parameters.

### Return Values

None

SolrPingResponse::\_\_destruct
==============================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrPingResponse::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Destructor

### Parameters

This function has no parameters.

### Return Values

None

SolrPingResponse::getResponse
=============================

Returns the response from the server

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrPingResponse::getResponse</span> ( <span
class="methodparam">void</span> )

Returns the response from the server. This should be empty because the
request as a HEAD request.

### Parameters

This function has no parameters.

### Return Values

Returns an empty string.

Introduction
------------

Represents a response from the solr server.

Class synopsis
--------------

**SolrGenericResponse**

<span class="ooclass"> <span class="modifier">final</span> class
**SolrGenericResponse** </span> <span class="ooclass"> <span
class="modifier">extends</span> **SolrResponse** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrGenericResponse::PARSE_SOLR_OBJ` <span class="initializer"> =
0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrGenericResponse::PARSE_SOLR_DOC` <span class="initializer"> =
1</span> ;

/\* Inherited properties \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrResponse::PARSE_SOLR_OBJ` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrResponse::PARSE_SOLR_DOC` <span class="initializer"> = 1</span> ;

<span class="modifier">protected</span> <span class="type">int</span>
`$http_status` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$parser_mode` ;

<span class="modifier">protected</span> <span class="type">bool</span>
`$success` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_status_message` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_request_url` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_request_headers` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_request` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_response_headers` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_raw_response` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$http_digested_response` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getDigestedResponse</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrResponse::getHttpStatus</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getHttpStatusMessage</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequest</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawRequestHeaders</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRawResponseHeaders</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrResponse::getRequestUrl</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrObject</span> <span
class="methodname">SolrResponse::getResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::setParseMode</span> (\[ <span
class="methodparam"><span class="type">int</span> `$parser_mode`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrResponse::success</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

SolrGenericResponse Class constants
-----------------------------------

**`SolrGenericResponse::PARSE_SOLR_OBJ`**  
Documents should be parsed as SolrObject instances

**`SolrGenericResponse::PARSE_SOLR_DOC`**  
Documents should be parsed as SolrDocument instances.

SolrGenericResponse::\_\_construct
==================================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrGenericResponse::\_\_construct</span> ( <span
class="methodparam">void</span> )

Constructor

### Parameters

This function has no parameters.

### Return Values

None

SolrGenericResponse::\_\_destruct
=================================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrGenericResponse::\_\_destruct</span> (
<span class="methodparam">void</span> )

Destructor.

### Parameters

This function has no parameters.

### Return Values

None

Introduction
------------

Represents a collection of name-value pairs sent to the Solr server
during a request.

Class synopsis
--------------

**SolrParams**

<span class="ooclass"> <span class="modifier">abstract</span> class
**SolrParams** </span> <span class="oointerface">implements <span
class="interfacename">Serializable</span> </span> {

/\* Methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">SolrParams</span> <span class="methodname">add</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span
class="type">SolrParams</span> <span class="methodname">addParam</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span class="methodname">get</span> (
<span class="methodparam"><span class="type">string</span>
`$param_name`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span class="methodname">getParam</span>
(\[ <span class="methodparam"><span class="type">string</span>
`$param_name`</span> \] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">getParams</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">getPreparedParams</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">void</span> <span class="methodname">set</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span
class="type">SolrParams</span> <span class="methodname">setParam</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">toString</span> (\[ <span class="methodparam"><span
class="type">bool</span> `$url_encode`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">void</span> <span
class="methodname">unserialize</span> ( <span class="methodparam"><span
class="type">string</span> `$serialized`</span> )

}

SolrParams::add
===============

This is an alias for SolrParams::addParam

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">SolrParams</span> <span
class="methodname">SolrParams::add</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

This is an alias for SolrParams::addParam

### Parameters

`name`  
The name of the parameter

`value`  
The value of the parameter

### Return Values

Returns a SolrParams instance on success

SolrParams::addParam
====================

Adds a parameter to the object

### Description

<span class="modifier">public</span> <span
class="type">SolrParams</span> <span
class="methodname">SolrParams::addParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

Adds a parameter to the object. This is used for parameters that can be
specified multiple times.

### Parameters

`name`  
Name of parameter

`value`  
Value of parameter

### Return Values

Returns a SolrParam object on success and **`FALSE`** on failure.

SolrParams::get
===============

This is an alias for SolrParams::getParam

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">SolrParams::get</span> ( <span
class="methodparam"><span class="type">string</span>
`$param_name`</span> )

This is an alias for SolrParams::getParam

### Parameters

`param_name`  
Then name of the parameter

### Return Values

Returns an array or string depending on the type of parameter

SolrParams::getParam
====================

Returns a parameter value

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">SolrParams::getParam</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$param_name`</span> \] )

Returns a parameter with name param\_name

### Parameters

`param_name`  
The name of the parameter

### Return Values

Returns a string or an array depending on the type of the parameter

SolrParams::getParams
=====================

Returns an array of non URL-encoded parameters

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">SolrParams::getParams</span> ( <span
class="methodparam">void</span> )

Returns an array of non URL-encoded parameters

### Parameters

This function has no parameters.

### Return Values

Returns an array of non URL-encoded parameters

SolrParams::getPreparedParams
=============================

Returns an array of URL-encoded parameters

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">SolrParams::getPreparedParams</span> ( <span
class="methodparam">void</span> )

Returns an array on URL-encoded parameters

### Parameters

This function has no parameters.

### Return Values

Returns an array on URL-encoded parameters

SolrParams::serialize
=====================

Used for custom serialization

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">SolrParams::serialize</span> ( <span
class="methodparam">void</span> )

Used for custom serialization

### Parameters

This function has no parameters.

### Return Values

Used for custom serialization

SolrParams::set
===============

An alias of SolrParams::setParam

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">void</span> <span
class="methodname">SolrParams::set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

An alias of SolrParams::setParam

### Parameters

`name`  
Then name of the parameter

`value`  
The parameter value

### Return Values

Returns an instance of the SolrParams object on success

SolrParams::setParam
====================

Sets the parameter to the specified value

### Description

<span class="modifier">public</span> <span
class="type">SolrParams</span> <span
class="methodname">SolrParams::setParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

Sets the query parameter to the specified value. This is used for
parameters that can only be specified once. Subsequent calls with the
same parameter name will override the existing value

### Parameters

`name`  
Name of the parameter

`value`  
Value of the parameter

### Return Values

Returns a SolrParam object on success and **`FALSE`** on value.

### Examples

**Example \#1 <span class="methodname">SolrParams::setParam</span>
example**

``` php
<?php

$param = new SolrParams();

$param->setParam('q', 'solr')->setParam('rows', 2);

?>
```

The above example will output something similar to:

SolrParams::toString
====================

Returns all the name-value pair parameters in the object

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">SolrParams::toString</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$url_encode`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Returns all the name-value pair parameters in the object

### Parameters

`url_encode`  
Whether to return URL-encoded values

### Return Values

Returns a string on success and **`FALSE`** on failure.

SolrParams::unserialize
=======================

Used for custom serialization

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">void</span> <span
class="methodname">SolrParams::unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

Used for custom serialization

### Parameters

`serialized`  
The serialized representation of the object

### Return Values

None

Introduction
------------

Represents a collection of name-value pairs sent to the Solr server
during a request.

Class synopsis
--------------

**SolrModifiableParams**

<span class="ooclass"> class **SolrModifiableParams** </span> <span
class="ooclass"> <span class="modifier">extends</span> **SolrParams**
</span> <span class="oointerface">implements <span
class="interfacename">Serializable</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">SolrParams</span> <span
class="methodname">SolrParams::add</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span
class="type">SolrParams</span> <span
class="methodname">SolrParams::addParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">SolrParams::get</span> ( <span
class="methodparam"><span class="type">string</span>
`$param_name`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">SolrParams::getParam</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$param_name`</span> \] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">SolrParams::getParams</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">SolrParams::getPreparedParams</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">SolrParams::serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">void</span> <span
class="methodname">SolrParams::set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span
class="type">SolrParams</span> <span
class="methodname">SolrParams::setParam</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">SolrParams::toString</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$url_encode`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">void</span> <span
class="methodname">SolrParams::unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

}

SolrModifiableParams::\_\_construct
===================================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrModifiableParams::\_\_construct</span> ( <span
class="methodparam">void</span> )

Constructor

### Parameters

This function has no parameters.

### Return Values

None

SolrModifiableParams::\_\_destruct
==================================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrModifiableParams::\_\_destruct</span> (
<span class="methodparam">void</span> )

Destructor

### Parameters

This function has no parameters.

### Return Values

None

Introduction
------------

Represents a collection of name-value pairs sent to the Solr server
during a request.

Class synopsis
--------------

**SolrQuery**

<span class="ooclass"> class **SolrQuery** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**SolrModifiableParams** </span> <span class="oointerface">implements
<span class="interfacename">Serializable</span> </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::ORDER_ASC` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::ORDER_DESC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::FACET_SORT_INDEX` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::FACET_SORT_COUNT` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::TERMS_SORT_INDEX` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::TERMS_SORT_COUNT` <span class="initializer"> = 1</span> ;

/\* Properties \*/

/\* Methods \*/

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addExpandFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addExpandSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$order`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addFacetDateField</span> ( <span
class="methodparam"><span class="type">string</span> `$dateField`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addFacetDateOther</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addFacetField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addFacetQuery</span> ( <span
class="methodparam"><span class="type">string</span>
`$facetQuery`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addGroupField</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addGroupFunction</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addGroupQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addGroupSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">int</span> `$order`</span>
\] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addHighlightField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addMltField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addMltQueryField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">float</span>
`$boost`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">int</span> `$order`<span
class="initializer"> = SolrQuery::ORDER\_DESC</span></span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addStatsFacet</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">addStatsField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">collapse</span> ( <span
class="methodparam"><span class="type">SolrCollapseFunction</span>
`$collapseFunction`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$q`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getExpand</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getExpandFilterQueries</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getExpandQuery</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getExpandRows</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getExpandSortFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getFacet</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFacetDateEnd</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getFacetDateFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFacetDateGap</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFacetDateHardEnd</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getFacetDateOther</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFacetDateStart</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getFacetFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFacetLimit</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFacetMethod</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFacetMinCount</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getFacetMissing</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFacetOffset</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFacetPrefix</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getFacetQueries</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFacetSort</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getFilterQueries</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getGroup</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getGroupCachePercent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getGroupFacet</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getGroupFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getGroupFormat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getGroupFunctions</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getGroupLimit</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getGroupMain</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getGroupNGroups</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getGroupOffset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getGroupQueries</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getGroupSortFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getGroupTruncate</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getHighlight</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getHighlightAlternateField</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getHighlightFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getHighlightFormatter</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getHighlightFragmenter</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getHighlightFragsize</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getHighlightHighlightMultiTerm</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getHighlightMaxAlternateFieldLength</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getHighlightMaxAnalyzedChars</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getHighlightMergeContiguous</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getHighlightRegexMaxAnalyzedChars</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getHighlightRegexPattern</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getHighlightRegexSlop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getHighlightRequireFieldMatch</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getHighlightSimplePost</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getHighlightSimplePre</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getHighlightSnippets</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getHighlightUsePhraseHighlighter</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getMlt</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getMltBoost</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getMltCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getMltFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getMltMaxNumQueryTerms</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getMltMaxNumTokens</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getMltMaxWordLength</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getMltMinDocFrequency</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getMltMinTermFrequency</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getMltMinWordLength</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getMltQueryFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getQuery</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getRows</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getSortFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getStart</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getStats</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getStatsFacets</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getStatsFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getTerms</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getTermsField</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getTermsIncludeLowerBound</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getTermsIncludeUpperBound</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTermsLimit</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getTermsLowerBound</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTermsMaxCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTermsMinCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getTermsPrefix</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getTermsReturnRaw</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTermsSort</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getTermsUpperBound</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTimeAllowed</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeExpandFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeExpandSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeFacetDateField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeFacetDateOther</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeFacetField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeFacetQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeHighlightField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeMltField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeMltQueryField</span> ( <span
class="methodparam"><span class="type">string</span>
`$queryField`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeStatsFacet</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">removeStatsField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setEchoHandler</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setEchoParams</span> ( <span
class="methodparam"><span class="type">string</span> `$type`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setExpand</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setExpandQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$q`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setExpandRows</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setExplainOther</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacet</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetDateEnd</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetDateGap</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetDateHardEnd</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetDateStart</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetEnumCacheMinDefaultFrequency</span> (
<span class="methodparam"><span class="type">int</span>
`$frequency`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$limit`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetMethod</span> ( <span
class="methodparam"><span class="type">string</span> `$method`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetMinCount</span> ( <span
class="methodparam"><span class="type">int</span> `$mincount`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetMissing</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetOffset</span> ( <span
class="methodparam"><span class="type">int</span> `$offset`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetPrefix</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setFacetSort</span> ( <span
class="methodparam"><span class="type">int</span> `$facetSort`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setGroup</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setGroupCachePercent</span> ( <span
class="methodparam"><span class="type">int</span> `$percent`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setGroupFacet</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setGroupFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setGroupLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setGroupMain</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setGroupNGroups</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setGroupOffset</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setGroupTruncate</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlight</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightAlternateField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightFormatter</span> ( <span
class="methodparam"><span class="type">string</span> `$formatter`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightFragmenter</span> ( <span
class="methodparam"><span class="type">string</span>
`$fragmenter`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightFragsize</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightHighlightMultiTerm</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightMaxAlternateFieldLength</span> (
<span class="methodparam"><span class="type">int</span>
`$fieldLength`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightMaxAnalyzedChars</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightMergeContiguous</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightRegexMaxAnalyzedChars</span> (
<span class="methodparam"><span class="type">int</span>
`$maxAnalyzedChars`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightRegexPattern</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightRegexSlop</span> ( <span
class="methodparam"><span class="type">float</span> `$factor`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightRequireFieldMatch</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightSimplePost</span> ( <span
class="methodparam"><span class="type">string</span>
`$simplePost`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightSimplePre</span> ( <span
class="methodparam"><span class="type">string</span> `$simplePre`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightSnippets</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setHighlightUsePhraseHighlighter</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setMlt</span> ( <span class="methodparam"><span
class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setMltBoost</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setMltCount</span> ( <span
class="methodparam"><span class="type">int</span> `$count`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setMltMaxNumQueryTerms</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setMltMaxNumTokens</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setMltMaxWordLength</span> ( <span
class="methodparam"><span class="type">int</span>
`$maxWordLength`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setMltMinDocFrequency</span> ( <span
class="methodparam"><span class="type">int</span>
`$minDocFrequency`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setMltMinTermFrequency</span> ( <span
class="methodparam"><span class="type">int</span>
`$minTermFrequency`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setMltMinWordLength</span> ( <span
class="methodparam"><span class="type">int</span>
`$minWordLength`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setOmitHeader</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setRows</span> ( <span
class="methodparam"><span class="type">int</span> `$rows`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setShowDebugInfo</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setStart</span> ( <span
class="methodparam"><span class="type">int</span> `$start`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setStats</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTerms</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldname`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsIncludeLowerBound</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsIncludeUpperBound</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$limit`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsLowerBound</span> ( <span
class="methodparam"><span class="type">string</span>
`$lowerBound`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsMaxCount</span> ( <span
class="methodparam"><span class="type">int</span> `$frequency`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsMinCount</span> ( <span
class="methodparam"><span class="type">int</span> `$frequency`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsPrefix</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsReturnRaw</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsSort</span> ( <span
class="methodparam"><span class="type">int</span> `$sortType`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTermsUpperBound</span> ( <span
class="methodparam"><span class="type">string</span>
`$upperBound`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">setTimeAllowed</span> ( <span
class="methodparam"><span class="type">int</span> `$timeAllowed`</span>
)

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">SolrModifiableParams::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrModifiableParams::\_\_destruct</span> (
<span class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`SolrQuery::ORDER_ASC`**  
Used to specify that the sorting should be in acending order

**`SolrQuery::ORDER_DESC`**  
Used to specify that the sorting should be in descending order

**`SolrQuery::FACET_SORT_INDEX`**  
Used to specify that the facet should sort by index

**`SolrQuery::FACET_SORT_COUNT`**  
Used to specify that the facet should sort by count

**`SolrQuery::TERMS_SORT_INDEX`**  
Used in the TermsComponent

**`SolrQuery::TERMS_SORT_COUNT`**  
Used in the TermsComponent

SolrQuery::addExpandFilterQuery
===============================

Overrides main filter query, determines which documents to include in
the main group

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addExpandFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

Overrides main filter query, determines which documents to include in
the main group.

### Parameters

`fq`  

### Return Values

<span class="type">SolrQuery</span>

### See Also

-   <span class="methodname">SolrQuery::setExpand</span>
-   <span class="methodname">SolrQuery::addExpandSortField</span>
-   <span class="methodname">SolrQuery::removeExpandSortField</span>
-   <span class="methodname">SolrQuery::setExpandRows</span>
-   <span class="methodname">SolrQuery::setExpandQuery</span>
-   <span class="methodname">SolrQuery::removeExpandFilterQuery</span>

SolrQuery::addExpandSortField
=============================

Orders the documents within the expanded groups (expand.sort parameter)

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addExpandSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$order`</span> \] )

Orders the documents within the expanded groups (expand.sort parameter).

### Parameters

`field`  
field name

`order`  
Order ASC/DESC, utilizes SolrQuery::ORDER\_\* constants.

Default: <span class="type">SolrQuery::ORDER\_DESC</span>

### Return Values

<span class="type">SolrQuery</span>

### See Also

-   <span class="methodname">SolrQuery::setExpand</span>
-   <span class="methodname">SolrQuery::removeExpandSortField</span>
-   <span class="methodname">SolrQuery::setExpandRows</span>
-   <span class="methodname">SolrQuery::setExpandQuery</span>
-   <span class="methodname">SolrQuery::addExpandFilterQuery</span>
-   <span class="methodname">SolrQuery::removeExpandFilterQuery</span>

SolrQuery::addFacetDateField
============================

Maps to facet.date

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFacetDateField</span> ( <span
class="methodparam"><span class="type">string</span> `$dateField`</span>
)

This method allows you to specify a field which should be treated as a
facet.

It can be used multiple times with different field names to indicate
multiple facet fields

### Parameters

`dateField`  
The name of the date field.

### Return Values

Returns a SolrQuery object.

SolrQuery::addFacetDateOther
============================

Adds another facet.date.other parameter

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFacetDateOther</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Sets the facet.date.other parameter. Accepts an optional field override

### Parameters

`value`  
The value to use.

`field_override`  
The field name for the override.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::addFacetField
========================

Adds another field to the facet

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFacetField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Adds another field to the facet

### Parameters

`field`  
The name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

### Examples

**Example \#1 <span class="methodname">SolrQuery::addFacetField</span>
example**

``` php
<?php

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
);

$client = new SolrClient($options);

$query = new SolrQuery();

$query->setQuery($query);

$query->addField('price')->addField('color');

$query->setFacet(true);

$query->addFacetField('price')->addFacetField('color');

$query_response = $client->query($query);

$response = $query_response->getResponse();

print_r($response['facet_counts']['facet_fields']);

?>
```

The above example will output something similar to:


    SolrObject Object
    (
        [color] => SolrObject Object
            (
                [blue] => 20
                [green] => 100
            )

    )

SolrQuery::addFacetQuery
========================

Adds a facet query

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFacetQuery</span> ( <span
class="methodparam"><span class="type">string</span>
`$facetQuery`</span> )

Adds a facet query

### Parameters

`facetQuery`  
The facet query

### Return Values

Returns the current SolrQuery object, if the return value is used.

### Examples

**Example \#1 <span class="methodname">SolrQuery::addFacetField</span>
example**

``` php
<?php

$options = array
(
        'hostname' => SOLR_SERVER_HOSTNAME,
        'login'    => SOLR_SERVER_USERNAME,
        'password' => SOLR_SERVER_PASSWORD,
        'port'     => SOLR_SERVER_PORT,
);

$client = new SolrClient($options);

$query = new SolrQuery('*:*');

$query->setFacet(true);

$query->addFacetQuery('price:[* TO 500]')->addFacetQuery('price:[500 TO *]');

$query_response = $client->query($query);

$response = $query_response->getResponse();

print_r($response->facet_counts->facet_queries);

?>
```

The above example will output something similar to:


    SolrObject Object
    (
        [price:[* TO 500]] => 14
        [price:[500 TO *]] => 2
    )

SolrQuery::addField
===================

Specifies which fields to return in the result

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

This method is used to used to specify a set of fields to return,
thereby restricting the amount of data returned in the response.

It should be called multiple time, once for each field name.

### Parameters

`field`  
The name of the field

### Return Values

Returns the current SolrQuery object

SolrQuery::addFilterQuery
=========================

Specifies a filter query

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

Specifies a filter query

### Parameters

`fq`  
The filter query

### Return Values

Returns the current SolrQuery object.

### Examples

**Example \#1 <span class="methodname">SolrQuery::addFilterQuery</span>
example**

``` php
<?php

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
);

$client = new SolrClient($options);

$query = new SolrQuery();

$query->setQuery('*:*');

$query->addFilterQuery('color:blue,green');

$query_response = $client->query($query);

$response = $query_response->getResponse();

print_r($response['facet_counts']['facet_fields']);

?>
```

The above example will output something similar to:

     &fq=color:blue,green

SolrQuery::addGroupField
========================

Add a field to be used to group results

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addGroupField</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

The name of the field by which to group results. The field must be
single-valued, and either be indexed or a field type that has a value
source and works in a function query, such as ExternalFileField. It must
also be a string-based field, such as StrField or TextField Uses
group.field parameter

### Parameters

`value`  

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::addGroupFunction
===========================

Allows grouping results based on the unique values of a function query
(group.func parameter)

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addGroupFunction</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Adds a group function (group.func parameter) Allows grouping results
based on the unique values of a function query.

### Parameters

`value`  

### Return Values

<span class="type">SolrQuery</span>

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::addGroupQuery
========================

Allows grouping of documents that match the given query

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addGroupQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Allows grouping of documents that match the given query. Adds query to
the group.query parameter

### Parameters

`value`  

### Return Values

<span class="type">SolrQuery</span>

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::addGroupSortField
============================

Add a group sort field (group.sort parameter)

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addGroupSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">int</span> `$order`</span>
\] )

Allow sorting group documents, using group sort field (group.sort
parameter).

### Parameters

`field`  
Field name

`order`  
Order ASC/DESC, utilizes SolrQuery::ORDER\_\* constants

### Return Values

### Examples

**Example \#1 <span class="function">SolrQuery::addGroupSortField</span>
example**

``` php
<?php

$solrQuery = new SolrQuery('*:*');
$solrQuery
    ->setGroup(true)
    ->addGroupSortField('price', SolrQuery::ORDER_ASC);
    
echo $solrQuery; 
?>
```

The above example will output something similar to:

    q=*:*&group=true&group.sort=price asc

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::addHighlightField
============================

Maps to hl.fl

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addHighlightField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Maps to hl.fl. This is used to specify that highlighted snippets should
be generated for a particular field

### Parameters

`field`  
Name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::addMltField
======================

Sets a field to use for similarity

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addMltField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Maps to mlt.fl. It specifies that a field should be used for similarity.

### Parameters

`field`  
The name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::addMltQueryField
===========================

Maps to mlt.qf

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addMltQueryField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">float</span>
`$boost`</span> )

Maps to mlt.qf. It is used to specify query fields and their boosts

### Parameters

`field`  
The name of the field

`boost`  
Its boost value

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::addSortField
=======================

Used to control how the results should be sorted

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">int</span> `$order`<span
class="initializer"> = SolrQuery::ORDER\_DESC</span></span> \] )

Used to control how the results should be sorted.

### Parameters

`field`  
The name of the field

`order`  
The sort direction. This should be either SolrQuery::ORDER\_ASC or
SolrQuery::ORDER\_DESC.

### Return Values

Returns the current SolrQuery object.

SolrQuery::addStatsFacet
========================

Requests a return of sub results for values within the given facet

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addStatsFacet</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Requests a return of sub results for values within the given facet. Maps
to the stats.facet field

### Parameters

`field`  
The name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::addStatsField
========================

Maps to stats.field parameter

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addStatsField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Maps to stats.field parameter This methods adds another stats.field
parameter.

### Parameters

`field`  
The name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::collapse
===================

Collapses the result set to a single document per group

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::collapse</span> ( <span
class="methodparam"><span class="type">SolrCollapseFunction</span>
`$collapseFunction`</span> )

Collapses the result set to a single document per group before it
forwards the result set to the rest of the search components.

So all downstream components (faceting, highlighting, etc...) will work
with the collapsed result set.

### Parameters

`collapseFunction`  

### Return Values

Returns the current <span class="type">SolrQuery</span> object

### Examples

**Example \#1 <span class="methodname">SolrQuery::collapse</span>
example**

``` php
<?php

include "bootstrap.php";

$options = array
(
        'hostname' => SOLR_SERVER_HOSTNAME,
        'login'    => SOLR_SERVER_USERNAME,
        'password' => SOLR_SERVER_PASSWORD,
        'port'     => SOLR_SERVER_PORT,
        'path'     => SOLR_SERVER_PATH
);

$client = new SolrClient($options);

$query = new SolrQuery('*:*');

$collapseFunction = new SolrCollapseFunction('manu_id_s');

$collapseFunction
->setSize(2)
->setNullPolicy(SolrCollapseFunction::NULLPOLICY_IGNORE);

$query
->collapse($collapseFunction)
->setRows(4);

$queryResponse = $client->query($query);

$response = $queryResponse->getResponse();

print_r($response);

?>
```

The above example will output something similar to:

    SolrObject Object
    (
        [responseHeader] => SolrObject Object
            (
                [status] => 0
                [QTime] => 1
                [params] => SolrObject Object
                    (
                        [q] => *:*
                        [indent] => on
                        [fq] => {!collapse field=manu_id_s size=2 nullPolicy=ignore}
                        [rows] => 4
                        [version] => 2.2
                        [wt] => xml
                    )

            )

        [response] => SolrObject Object
            (
                [numFound] => 14
                [start] => 0
                [docs] => Array
                    (
                        [0] => SolrObject Object
                            (
                                [id] => SP2514N
                                [name] => Array
                                    (
                                        [0] => Samsung SpinPoint P120 SP2514N - hard drive - 250 GB - ATA-133
                                    )

                                [manu] => Array
                                    (
                                        [0] => Samsung Electronics Co. Ltd.
                                    )

                                [manu_id_s] => samsung
                                [cat] => Array
                                    (
                                        [0] => electronics
                                        [1] => hard drive
                                    )

                                [features] => Array
                                    (
                                        [0] => 7200RPM, 8MB cache, IDE Ultra ATA-133
                                        [1] => NoiseGuard, SilentSeek technology, Fluid Dynamic Bearing (FDB) motor
                                    )

                                [price] => Array
                                    (
                                        [0] => 92
                                    )

                                [popularity] => Array
                                    (
                                        [0] => 6
                                    )

                                [inStock] => Array
                                    (
                                        [0] => 1
                                    )

                                [manufacturedate_dt] => 2006-02-13T15:26:37Z
                                [store] => Array
                                    (
                                        [0] => 35.0752,-97.032
                                    )

                                [_version_] => 1510294336412057600
                            )

                        [1] => SolrObject Object
                            (
                                [id] => 6H500F0
                                [name] => Array
                                    (
                                        [0] => Maxtor DiamondMax 11 - hard drive - 500 GB - SATA-300
                                    )

                                [manu] => Array
                                    (
                                        [0] => Maxtor Corp.
                                    )

                                [manu_id_s] => maxtor
                                [cat] => Array
                                    (
                                        [0] => electronics
                                        [1] => hard drive
                                    )

                                [features] => Array
                                    (
                                        [0] => SATA 3.0Gb/s, NCQ
                                        [1] => 8.5ms seek
                                        [2] => 16MB cache
                                    )

                                [price] => Array
                                    (
                                        [0] => 350
                                    )

                                [popularity] => Array
                                    (
                                        [0] => 6
                                    )

                                [inStock] => Array
                                    (
                                        [0] => 1
                                    )

                                [store] => Array
                                    (
                                        [0] => 45.17614,-93.87341
                                    )

                                [manufacturedate_dt] => 2006-02-13T15:26:37Z
                                [_version_] => 1510294336449806336
                            )

                        [2] => SolrObject Object
                            (
                                [id] => F8V7067-APL-KIT
                                [name] => Array
                                    (
                                        [0] => Belkin Mobile Power Cord for iPod w/ Dock
                                    )

                                [manu] => Array
                                    (
                                        [0] => Belkin
                                    )

                                [manu_id_s] => belkin
                                [cat] => Array
                                    (
                                        [0] => electronics
                                        [1] => connector
                                    )

                                [features] => Array
                                    (
                                        [0] => car power adapter, white
                                    )

                                [weight] => Array
                                    (
                                        [0] => 4
                                    )

                                [price] => Array
                                    (
                                        [0] => 19.95
                                    )

                                [popularity] => Array
                                    (
                                        [0] => 1
                                    )

                                [inStock] => Array
                                    (
                                        [0] => 
                                    )

                                [store] => Array
                                    (
                                        [0] => 45.18014,-93.87741
                                    )

                                [manufacturedate_dt] => 2005-08-01T16:30:25Z
                                [_version_] => 1510294336458194944
                            )

                        [3] => SolrObject Object
                            (
                                [id] => MA147LL/A
                                [name] => Array
                                    (
                                        [0] => Apple 60 GB iPod with Video Playback Black
                                    )

                                [manu] => Array
                                    (
                                        [0] => Apple Computer Inc.
                                    )

                                [manu_id_s] => apple
                                [cat] => Array
                                    (
                                        [0] => electronics
                                        [1] => music
                                    )

                                [features] => Array
                                    (
                                        [0] => iTunes, Podcasts, Audiobooks
                                        [1] => Stores up to 15,000 songs, 25,000 photos, or 150 hours of video
                                        [2] => 2.5-inch, 320x240 color TFT LCD display with LED backlight
                                        [3] => Up to 20 hours of battery life
                                        [4] => Plays AAC, MP3, WAV, AIFF, Audible, Apple Lossless, H.264 video
                                        [5] => Notes, Calendar, Phone book, Hold button, Date display, Photo wallet, Built-in games, JPEG photo playback, Upgradeable firmware, USB 2.0 compatibility, Playback speed control, Rechargeable capability, Battery level indication
                                    )

                                [includes] => Array
                                    (
                                        [0] => earbud headphones, USB cable
                                    )

                                [weight] => Array
                                    (
                                        [0] => 5.5
                                    )

                                [price] => Array
                                    (
                                        [0] => 399
                                    )

                                [popularity] => Array
                                    (
                                        [0] => 10
                                    )

                                [inStock] => Array
                                    (
                                        [0] => 1
                                    )

                                [store] => Array
                                    (
                                        [0] => 37.7752,-100.0232
                                    )

                                [manufacturedate_dt] => 2005-10-12T08:00:00Z
                                [_version_] => 1510294336562003968
                            )

                    )

            )

    )

SolrQuery::\_\_construct
========================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrQuery::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$q`</span> \] )

Constructor.

### Parameters

`q`  
Optional search query

### Return Values

None

### Errors/Exceptions

Emits <span class="classname">SolrIllegalArgumentException</span> in
case of an invalid parameter was passed.

### Changelog

| Version         | Description                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
| PECL solr 2.0.0 | If `q` was invalid, then a <span class="classname">SolrIllegalArgumentException</span> is now thrown. Previously an error was emitted. |

SolrQuery::\_\_destruct
=======================

Destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrQuery::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Destructor

### Parameters

This function has no parameters.

### Return Values

None.

SolrQuery::getExpand
====================

Returns true if group expanding is enabled

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getExpand</span> ( <span
class="methodparam">void</span> )

Returns **`TRUE`** if group expanding is enabled

SolrQuery::getExpandFilterQueries
=================================

Returns the expand filter queries

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getExpandFilterQueries</span> (
<span class="methodparam">void</span> )

Returns the expand filter queries

SolrQuery::getExpandQuery
=========================

Returns the expand query expand.q parameter

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getExpandQuery</span> ( <span
class="methodparam">void</span> )

Returns the expand query expand.q parameter

SolrQuery::getExpandRows
========================

Returns The number of rows to display in each group (expand.rows)

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getExpandRows</span> ( <span
class="methodparam">void</span> )

Returns The number of rows to display in each group (expand.rows)

SolrQuery::getExpandSortFields
==============================

Returns an array of fields

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getExpandSortFields</span> ( <span
class="methodparam">void</span> )

Returns an array of fields

SolrQuery::getFacet
===================

Returns the value of the facet parameter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getFacet</span> ( <span
class="methodparam">void</span> )

Returns the value of the facet parameter.

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set

SolrQuery::getFacetDateEnd
==========================

Returns the value for the facet.date.end parameter

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetDateEnd</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the value for the facet.date.end parameter. This method accepts
an optional field override

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set

SolrQuery::getFacetDateFields
=============================

Returns all the facet.date fields

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFacetDateFields</span> ( <span
class="methodparam">void</span> )

Returns all the facet.date fields

### Parameters

This function has no parameters.

### Return Values

Returns all the facet.date fields as an array or **`NULL`** if none was
set

SolrQuery::getFacetDateGap
==========================

Returns the value of the facet.date.gap parameter

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetDateGap</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the value of the facet.date.gap parameter. It accepts an
optional field override

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set

SolrQuery::getFacetDateHardEnd
==============================

Returns the value of the facet.date.hardend parameter

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetDateHardEnd</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the value of the facet.date.hardend parameter. Accepts an
optional field override

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set

SolrQuery::getFacetDateOther
============================

Returns the value for the facet.date.other parameter

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFacetDateOther</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the value for the facet.date.other parameter. This method
accepts an optional field override.

### Parameters

`field_override`  
The name of the field

### Return Values

Returns an <span class="type">array</span> on success and **`NULL`** if
not set.

SolrQuery::getFacetDateStart
============================

Returns the lower bound for the first date range for all date faceting
on this field

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetDateStart</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the lower bound for the first date range for all date faceting
on this field. Accepts an optional field override

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set

SolrQuery::getFacetFields
=========================

Returns all the facet fields

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFacetFields</span> ( <span
class="methodparam">void</span> )

Returns all the facet fields

### Parameters

This function has no parameters.

### Return Values

Returns an array of all the fields and **`NULL`** if none was set

SolrQuery::getFacetLimit
========================

Returns the maximum number of constraint counts that should be returned
for the facet fields

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getFacetLimit</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the maximum number of constraint counts that should be returned
for the facet fields. This method accepts an optional field override

### Parameters

`field_override`  
The name of the field to override for

### Return Values

Returns an integer on success and **`NULL`** if not set

SolrQuery::getFacetMethod
=========================

Returns the value of the facet.method parameter

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetMethod</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the value of the facet.method parameter. This accepts an
optional field override.

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set

SolrQuery::getFacetMinCount
===========================

Returns the minimum counts for facet fields should be included in the
response

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getFacetMinCount</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the minimum counts for facet fields should be included in the
response. It accepts an optional field override

### Parameters

`field_override`  
The name of the field

### Return Values

Returns an integer on success and **`NULL`** if not set

SolrQuery::getFacetMissing
==========================

Returns the current state of the facet.missing parameter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getFacetMissing</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the current state of the facet.missing parameter. This accepts
an optional field override

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a boolean on success and **`NULL`** if not set

SolrQuery::getFacetOffset
=========================

Returns an offset into the list of constraints to be used for pagination

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getFacetOffset</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns an offset into the list of constraints to be used for
pagination. Accepts an optional field override

### Parameters

`field_override`  
The name of the field to override for.

### Return Values

Returns an integer on success and **`NULL`** if not set

SolrQuery::getFacetPrefix
=========================

Returns the facet prefix

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetPrefix</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the facet prefix

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getFacetQueries
==========================

Returns all the facet queries

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFacetQueries</span> ( <span
class="methodparam">void</span> )

Returns all the facet queries

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`NULL`** if not set.

SolrQuery::getFacetSort
=======================

Returns the facet sort type

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getFacetSort</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns an integer (SolrQuery::FACET\_SORT\_INDEX or
SolrQuery::FACET\_SORT\_COUNT)

### Parameters

`field_override`  
The name of the field

### Return Values

Returns an integer (SolrQuery::FACET\_SORT\_INDEX or
SolrQuery::FACET\_SORT\_COUNT) on success or **`NULL`** if not set.

SolrQuery::getFields
====================

Returns the list of fields that will be returned in the response

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFields</span> ( <span
class="methodparam">void</span> )

Returns the list of fields that will be returned in the response

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`NULL`** if not set.

SolrQuery::getFilterQueries
===========================

Returns an array of filter queries

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFilterQueries</span> ( <span
class="methodparam">void</span> )

Returns an array of filter queries. These are queries that can be used
to restrict the super set of documents that can be returned, without
influencing score

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`NULL`** if not set.

SolrQuery::getGroup
===================

Returns true if grouping is enabled

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroup</span> ( <span
class="methodparam">void</span> )

Returns true if grouping is enabled

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>

SolrQuery::getGroupCachePercent
===============================

Returns group cache percent value

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getGroupCachePercent</span> ( <span
class="methodparam">void</span> )

Returns group cache percent value

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::getGroupFacet
========================

Returns the group.facet parameter value

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroupFacet</span> ( <span
class="methodparam">void</span> )

Returns the group.facet parameter value

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroupFacet</span>

SolrQuery::getGroupFields
=========================

Returns group fields (group.field parameter values)

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getGroupFields</span> ( <span
class="methodparam">void</span> )

Returns group fields (group.field parameter values)

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::addGroupField</span>

SolrQuery::getGroupFormat
=========================

Returns the group.format value

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getGroupFormat</span> ( <span
class="methodparam">void</span> )

Returns the group.format value

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroupFormat</span>

SolrQuery::getGroupFunctions
============================

Returns group functions (group.func parameter values)

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getGroupFunctions</span> ( <span
class="methodparam">void</span> )

Returns group functions (group.func parameter values)

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::addGroupFunction</span>

SolrQuery::getGroupLimit
========================

Returns the group.limit value

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getGroupLimit</span> ( <span
class="methodparam">void</span> )

Returns the group.limit value

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroupLimit</span>

SolrQuery::getGroupMain
=======================

Returns the group.main value

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroupMain</span> ( <span
class="methodparam">void</span> )

Returns the group.main value

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroupMain</span>

SolrQuery::getGroupNGroups
==========================

Returns the group.ngroups value

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroupNGroups</span> ( <span
class="methodparam">void</span> )

Returns the group.ngroups value

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroupNGroups</span>

SolrQuery::getGroupOffset
=========================

Returns the group.offset value

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getGroupOffset</span> ( <span
class="methodparam">void</span> )

Returns the group.offset value

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroupOffset</span>

SolrQuery::getGroupQueries
==========================

Returns all the group.query parameter values

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getGroupQueries</span> ( <span
class="methodparam">void</span> )

Returns all the group.query parameter values

### Parameters

This function has no parameters.

### Return Values

<span class="type">array</span>

### See Also

-   <span class="methodname">SolrQuery::addGroupQuery</span>

SolrQuery::getGroupSortFields
=============================

Returns the group.sort value

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getGroupSortFields</span> ( <span
class="methodparam">void</span> )

Returns the group.sort value

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::addGroupSortField</span>

SolrQuery::getGroupTruncate
===========================

Returns the group.truncate value

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroupTruncate</span> ( <span
class="methodparam">void</span> )

Returns the group.truncate value

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroupTruncate</span>

SolrQuery::getHighlight
=======================

Returns the state of the hl parameter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getHighlight</span> ( <span
class="methodparam">void</span> )

Returns a boolean indicating whether or not to enable highlighted
snippets to be generated in the query response.

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getHighlightAlternateField
=====================================

Returns the highlight field to use as backup or default

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightAlternateField</span>
(\[ <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the highlight field to use as backup or default. It accepts an
optional override.

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getHighlightFields
=============================

Returns all the fields that Solr should generate highlighted snippets
for

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getHighlightFields</span> ( <span
class="methodparam">void</span> )

Returns all the fields that Solr should generate highlighted snippets
for

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`NULL`** if not set.

SolrQuery::getHighlightFormatter
================================

Returns the formatter for the highlighted output

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightFormatter</span> (\[
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the formatter for the highlighted output

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getHighlightFragmenter
=================================

Returns the text snippet generator for highlighted text

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightFragmenter</span> (\[
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the text snippet generator for highlighted text. Accepts an
optional field override.

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getHighlightFragsize
===============================

Returns the number of characters of fragments to consider for
highlighting

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightFragsize</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the number of characters of fragments to consider for
highlighting. Zero implies no fragmenting. The entire field should be
used.

### Parameters

`field_override`  
The name of the field

### Return Values

Returns an integer on success or **`NULL`** if not set.

SolrQuery::getHighlightHighlightMultiTerm
=========================================

Returns whether or not to enable highlighting for
range/wildcard/fuzzy/prefix queries

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">SolrQuery::getHighlightHighlightMultiTerm</span> (
<span class="methodparam">void</span> )

Returns whether or not to enable highlighting for
range/wildcard/fuzzy/prefix queries

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getHighlightMaxAlternateFieldLength
==============================================

Returns the maximum number of characters of the field to return

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightMaxAlternateFieldLength</span>
(\[ <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the maximum number of characters of the field to return

### Parameters

`field_override`  
The name of the field

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getHighlightMaxAnalyzedChars
=======================================

Returns the maximum number of characters into a document to look for
suitable snippets

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightMaxAnalyzedChars</span> (
<span class="methodparam">void</span> )

Returns the maximum number of characters into a document to look for
suitable snippets

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getHighlightMergeContiguous
======================================

Returns whether or not the collapse contiguous fragments into a single
fragment

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getHighlightMergeContiguous</span>
(\[ <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns whether or not the collapse contiguous fragments into a single
fragment. Accepts an optional field override.

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getHighlightRegexMaxAnalyzedChars
============================================

Returns the maximum number of characters from a field when using the
regex fragmenter

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightRegexMaxAnalyzedChars</span> (
<span class="methodparam">void</span> )

Returns the maximum number of characters from a field when using the
regex fragmenter

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getHighlightRegexPattern
===================================

Returns the regular expression for fragmenting

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightRegexPattern</span> (
<span class="methodparam">void</span> )

Returns the regular expression used for fragmenting

### Parameters

This function has no parameters.

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getHighlightRegexSlop
================================

Returns the deviation factor from the ideal fragment size

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">SolrQuery::getHighlightRegexSlop</span> ( <span
class="methodparam">void</span> )

Returns the factor by which the regex fragmenter can deviate from the
ideal fragment size to accomodate the regular expression

### Parameters

This function has no parameters.

### Return Values

Returns a double on success and **`NULL`** if not set.

SolrQuery::getHighlightRequireFieldMatch
========================================

Returns if a field will only be highlighted if the query matched in this
particular field

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getHighlightRequireFieldMatch</span>
( <span class="methodparam">void</span> )

Returns if a field will only be highlighted if the query matched in this
particular field.

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getHighlightSimplePost
=================================

Returns the text which appears after a highlighted term

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightSimplePost</span> (\[
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the text which appears after a highlighted term. Accepts an
optional field override

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getHighlightSimplePre
================================

Returns the text which appears before a highlighted term

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightSimplePre</span> (\[
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the text which appears before a highlighted term. Accepts an
optional field override

### Parameters

`field_override`  
The name of the field

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getHighlightSnippets
===============================

Returns the maximum number of highlighted snippets to generate per field

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightSnippets</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Returns the maximum number of highlighted snippets to generate per
field. Accepts an optional field override

### Parameters

`field_override`  
The name of the field

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getHighlightUsePhraseHighlighter
===========================================

Returns the state of the hl.usePhraseHighlighter parameter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">SolrQuery::getHighlightUsePhraseHighlighter</span> (
<span class="methodparam">void</span> )

Returns whether or not to use SpanScorer to highlight phrase terms only
when they appear within the query phrase in the document.

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getMlt
=================

Returns whether or not MoreLikeThis results should be enabled

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getMlt</span> ( <span
class="methodparam">void</span> )

Returns whether or not MoreLikeThis results should be enabled

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getMltBoost
======================

Returns whether or not the query will be boosted by the interesting term
relevance

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getMltBoost</span> ( <span
class="methodparam">void</span> )

Returns whether or not the query will be boosted by the interesting term
relevance

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getMltCount
======================

Returns the number of similar documents to return for each result

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltCount</span> ( <span
class="methodparam">void</span> )

Returns the number of similar documents to return for each result

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getMltFields
=======================

Returns all the fields to use for similarity

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getMltFields</span> ( <span
class="methodparam">void</span> )

Returns all the fields to use for similarity

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`NULL`** if not set.

SolrQuery::getMltMaxNumQueryTerms
=================================

Returns the maximum number of query terms that will be included in any
generated query

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMaxNumQueryTerms</span> ( <span
class="methodparam">void</span> )

Returns the maximum number of query terms that will be included in any
generated query

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getMltMaxNumTokens
=============================

Returns the maximum number of tokens to parse in each document field
that is not stored with TermVector support

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMaxNumTokens</span> ( <span
class="methodparam">void</span> )

Returns the maximum number of tokens to parse in each document field
that is not stored with TermVector support

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getMltMaxWordLength
==============================

Returns the maximum word length above which words will be ignored

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMaxWordLength</span> ( <span
class="methodparam">void</span> )

Returns the maximum word length above which words will be ignored

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getMltMinDocFrequency
================================

Returns the treshold frequency at which words will be ignored which do
not occur in at least this many docs

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMinDocFrequency</span> ( <span
class="methodparam">void</span> )

Returns the treshold frequency at which words will be ignored which do
not occur in at least this many docs

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getMltMinTermFrequency
=================================

Returns the frequency below which terms will be ignored in the source
document

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMinTermFrequency</span> ( <span
class="methodparam">void</span> )

Returns the frequency below which terms will be ignored in the source
document

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getMltMinWordLength
==============================

Returns the minimum word length below which words will be ignored

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMinWordLength</span> ( <span
class="methodparam">void</span> )

Returns the minimum word length below which words will be ignored

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getMltQueryFields
============================

Returns the query fields and their boosts

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getMltQueryFields</span> ( <span
class="methodparam">void</span> )

Returns the query fields and their boosts

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`NULL`** if not set.

SolrQuery::getQuery
===================

Returns the main query

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getQuery</span> ( <span
class="methodparam">void</span> )

Returns the main search query

### Parameters

This function has no parameters.

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getRows
==================

Returns the maximum number of documents

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getRows</span> ( <span
class="methodparam">void</span> )

Returns the maximum number of documents from the complete result set to
return to the client for every request

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getSortFields
========================

Returns all the sort fields

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getSortFields</span> ( <span
class="methodparam">void</span> )

Returns all the sort fields

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`NULL`** if none of the parameters was
set.

SolrQuery::getStart
===================

Returns the offset in the complete result set

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getStart</span> ( <span
class="methodparam">void</span> )

Returns the offset in the complete result set for the queries where the
set of returned documents should begin.

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getStats
===================

Returns whether or not stats is enabled

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getStats</span> ( <span
class="methodparam">void</span> )

Returns whether or not stats is enabled

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getStatsFacets
=========================

Returns all the stats facets that were set

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getStatsFacets</span> ( <span
class="methodparam">void</span> )

Returns all the stats facets that were set

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`NULL`** if not set.

SolrQuery::getStatsFields
=========================

Returns all the statistics fields

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getStatsFields</span> ( <span
class="methodparam">void</span> )

Returns all the statistics fields

### Parameters

This function has no parameters.

### Return Values

Returns an array on success and **`NULL`** if not set.

SolrQuery::getTerms
===================

Returns whether or not the TermsComponent is enabled

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getTerms</span> ( <span
class="methodparam">void</span> )

Returns whether or not the TermsComponent is enabled

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getTermsField
========================

Returns the field from which the terms are retrieved

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getTermsField</span> ( <span
class="methodparam">void</span> )

Returns the field from which the terms are retrieved

### Parameters

This function has no parameters.

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getTermsIncludeLowerBound
====================================

Returns whether or not to include the lower bound in the result set

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getTermsIncludeLowerBound</span> (
<span class="methodparam">void</span> )

Returns whether or not to include the lower bound in the result set

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getTermsIncludeUpperBound
====================================

Returns whether or not to include the upper bound term in the result set

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getTermsIncludeUpperBound</span> (
<span class="methodparam">void</span> )

Returns whether or not to include the upper bound term in the result set

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getTermsLimit
========================

Returns the maximum number of terms Solr should return

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTermsLimit</span> ( <span
class="methodparam">void</span> )

Returns the maximum number of terms Solr should return

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getTermsLowerBound
=============================

Returns the term to start at

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getTermsLowerBound</span> ( <span
class="methodparam">void</span> )

Returns the term to start at

### Parameters

This function has no parameters.

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getTermsMaxCount
===========================

Returns the maximum document frequency

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTermsMaxCount</span> ( <span
class="methodparam">void</span> )

Returns the maximum document frequency

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getTermsMinCount
===========================

Returns the minimum document frequency to return in order to be included

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTermsMinCount</span> ( <span
class="methodparam">void</span> )

Returns the minimum document frequency to return in order to be included

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getTermsPrefix
=========================

Returns the term prefix

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getTermsPrefix</span> ( <span
class="methodparam">void</span> )

Returns the prefix to which matching terms must be restricted. This will
restrict matches to only terms that start with the prefix

### Parameters

This function has no parameters.

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getTermsReturnRaw
============================

Whether or not to return raw characters

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getTermsReturnRaw</span> ( <span
class="methodparam">void</span> )

Returns a boolean indicating whether or not to return the raw characters
of the indexed term, regardless of if it is human readable

### Parameters

This function has no parameters.

### Return Values

Returns a boolean on success and **`NULL`** if not set.

SolrQuery::getTermsSort
=======================

Returns an integer indicating how terms are sorted

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTermsSort</span> ( <span
class="methodparam">void</span> )

SolrQuery::TERMS\_SORT\_INDEX indicates that the terms are returned by
index order. SolrQuery::TERMS\_SORT\_COUNT implies that the terms are
sorted by term frequency (highest count first)

### Parameters

This function has no parameters.

### Return Values

Returns an integer on success and **`NULL`** if not set.

SolrQuery::getTermsUpperBound
=============================

Returns the term to stop at

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getTermsUpperBound</span> ( <span
class="methodparam">void</span> )

Returns the term to stop at

### Parameters

This function has no parameters.

### Return Values

Returns a string on success and **`NULL`** if not set.

SolrQuery::getTimeAllowed
=========================

Returns the time in milliseconds allowed for the query to finish

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTimeAllowed</span> ( <span
class="methodparam">void</span> )

Returns the time in milliseconds allowed for the query to finish.

### Parameters

This function has no parameters.

### Return Values

Returns and integer on success and **`NULL`** if it is not set.

SolrQuery::removeExpandFilterQuery
==================================

Removes an expand filter query

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeExpandFilterQuery</span> (
<span class="methodparam"><span class="type">string</span> `$fq`</span>
)

Removes an expand filter query.

### Parameters

`fq`  

### Return Values

<span class="type">SolrQuery</span>

### See Also

-   <span class="methodname">SolrQuery::setExpand</span>
-   <span class="methodname">SolrQuery::addExpandSortField</span>
-   <span class="methodname">SolrQuery::removeExpandSortField</span>
-   <span class="methodname">SolrQuery::setExpandRows</span>
-   <span class="methodname">SolrQuery::setExpandQuery</span>
-   <span class="methodname">SolrQuery::addExpandFilterQuery</span>

SolrQuery::removeExpandSortField
================================

Removes an expand sort field from the expand.sort parameter

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeExpandSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes an expand sort field from the expand.sort parameter.

### Parameters

`field`  
field name

### Return Values

<span class="type">SolrQuery</span>

### See Also

-   <span class="methodname">SolrQuery::setExpand</span>
-   <span class="methodname">SolrQuery::addExpandSortField</span>
-   <span class="methodname">SolrQuery::setExpandRows</span>
-   <span class="methodname">SolrQuery::setExpandQuery</span>
-   <span class="methodname">SolrQuery::addExpandFilterQuery</span>
-   <span class="methodname">SolrQuery::removeExpandFilterQuery</span>

SolrQuery::removeFacetDateField
===============================

Removes one of the facet date fields

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFacetDateField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

The name of the field

### Parameters

`field`  
The name of the date field to remove

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeFacetDateOther
===============================

Removes one of the facet.date.other parameters

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFacetDateOther</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Removes one of the facet.date.other parameters

### Parameters

`value`  
The value

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeFacetField
===========================

Removes one of the facet.date parameters

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFacetField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes one of the facet.date parameters

### Parameters

`field`  
The name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeFacetQuery
===========================

Removes one of the facet.query parameters

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFacetQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Removes one of the facet.query parameters.

### Parameters

`value`  
The value

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeField
======================

Removes a field from the list of fields

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes a field from the list of fields

### Parameters

`field`  
Name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeFilterQuery
============================

Removes a filter query

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

Removes a filter query.

### Parameters

`fq`  
The filter query to remove

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeHighlightField
===============================

Removes one of the fields used for highlighting

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeHighlightField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes one of the fields used for highlighting.

### Parameters

`field`  
The name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeMltField
=========================

Removes one of the moreLikeThis fields

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeMltField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes one of the moreLikeThis fields.

### Parameters

`field`  
Name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeMltQueryField
==============================

Removes one of the moreLikeThis query fields

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeMltQueryField</span> ( <span
class="methodparam"><span class="type">string</span>
`$queryField`</span> )

Removes one of the moreLikeThis query fields.

### Parameters

`queryField`  
The query field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeSortField
==========================

Removes one of the sort fields

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes one of the sort fields

### Parameters

`field`  
The name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeStatsFacet
===========================

Removes one of the stats.facet parameters

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeStatsFacet</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Removes one of the stats.facet parameters

### Parameters

`value`  
The value

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::removeStatsField
===========================

Removes one of the stats.field parameters

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeStatsField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes one of the stats.field parameters

### Parameters

`field`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setEchoHandler
=========================

Toggles the echoHandler parameter

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setEchoHandler</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

If set to true, Solr places the name of the handle used in the response
to the client for debugging purposes.

### Parameters

`flag`  
**`TRUE`** or **`FALSE`**

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setEchoParams
========================

Determines what kind of parameters to include in the response

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setEchoParams</span> ( <span
class="methodparam"><span class="type">string</span> `$type`</span> )

Instructs Solr what kinds of Request parameters should be included in
the response for debugging purposes, legal values include:

``` description
- none - don't include any request parameters for debugging
- explicit - include the parameters explicitly specified by the client in the request
- all - include all parameters involved in this request, either specified explicitly by the client, or implicit because of the request handler configuration.
```

### Parameters

`type`  
The type of parameters to include

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setExpand
====================

Enables/Disables the Expand Component

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setExpand</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

Enables/Disables the Expand Component.

### Parameters

`value`  
Bool flag

### Return Values

<span class="type">SolrQuery</span>

### Examples

**Example \#1 <span class="function">SolrQuery::setExpand</span>
example**

``` php
<?php

$query = new SolrQuery('lucene');

$query
    ->setExpand(true)
    ->setExpandRows(50)
    ->setExpandQuery('text:product')
    ->addExpandFilterQuery('manu:apple')
    ->addExpandFilterQuery('inStock:true')
    ->addExpandSortField('score', SolrQuery::ORDER_DESC)
    ->addExpandSortField('title', SolrQuery::ORDER_ASC);

echo $query.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&expand=true&expand.rows=50&expand.q=text:product&expand.fq=manu:apple&expand.fq=inStock:true&expand.sort=score desc,title asc

### See Also

-   <span class="methodname">SolrQuery::addExpandSortField</span>
-   <span class="methodname">SolrQuery::removeExpandSortField</span>
-   <span class="methodname">SolrQuery::setExpandRows</span>
-   <span class="methodname">SolrQuery::setExpandQuery</span>
-   <span class="methodname">SolrQuery::addExpandFilterQuery</span>
-   <span class="methodname">SolrQuery::removeExpandFilterQuery</span>

SolrQuery::setExpandQuery
=========================

Sets the expand.q parameter

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setExpandQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$q`</span> )

Sets the expand.q parameter.

Overrides the main q parameter, determines which documents to include in
the main group.

### Parameters

`q`  

### Return Values

<span class="type">SolrQuery</span>

### See Also

-   <span class="methodname">SolrQuery::setExpand</span>
-   <span class="methodname">SolrQuery::addExpandSortField</span>
-   <span class="methodname">SolrQuery::removeExpandSortField</span>
-   <span class="methodname">SolrQuery::setExpandRows</span>
-   <span class="methodname">SolrQuery::addExpandFilterQuery</span>
-   <span class="methodname">SolrQuery::removeExpandFilterQuery</span>

SolrQuery::setExpandRows
========================

Sets the number of rows to display in each group (expand.rows). Server
Default 5

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setExpandRows</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

Sets the number of rows to display in each group (expand.rows). Server
Default 5

### Parameters

`value`  

### Return Values

<span class="type">SolrQuery</span>

### See Also

-   <span class="methodname">SolrQuery::setExpand</span>
-   <span class="methodname">SolrQuery::addExpandSortField</span>
-   <span class="methodname">SolrQuery::removeExpandSortField</span>
-   <span class="methodname">SolrQuery::setExpandQuery</span>
-   <span class="methodname">SolrQuery::addExpandFilterQuery</span>
-   <span class="methodname">SolrQuery::removeExpandFilterQuery</span>

SolrQuery::setExplainOther
==========================

Sets the explainOther common query parameter

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setExplainOther</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

Sets the explainOther common query parameter

### Parameters

`query`  
The Lucene query to identify a set of documents

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacet
===================

Maps to the facet parameter. Enables or disables facetting

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacet</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

Enables or disables faceting.

### Parameters

`value`  
**`TRUE`** enables faceting and **`FALSE`** disables it.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetDateEnd
==========================

Maps to facet.date.end

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetDateEnd</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Maps to facet.date.end

### Parameters

`value`  
See facet.date.end

`field_override`  
Name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetDateGap
==========================

Maps to facet.date.gap

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetDateGap</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Maps to facet.date.gap

### Parameters

`value`  
See facet.date.gap

`field_override`  
The name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetDateHardEnd
==============================

Maps to facet.date.hardend

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetDateHardEnd</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Maps to facet.date.hardend

### Parameters

`value`  
See facet.date.hardend

`field_override`  
The name of the field

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetDateStart
============================

Maps to facet.date.start

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetDateStart</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Maps to facet.date.start

### Parameters

`value`  
See facet.date.start

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetEnumCacheMinDefaultFrequency
===============================================

Sets the minimum document frequency used for determining term count

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setFacetEnumCacheMinDefaultFrequency</span>
( <span class="methodparam"><span class="type">int</span>
`$frequency`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

Sets the minimum document frequency used for determining term count

### Parameters

`value`  
The minimum frequency

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetLimit
========================

Maps to facet.limit

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$limit`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Maps to facet.limit. Sets the maximum number of constraint counts that
should be returned for the facet fields.

### Parameters

`limit`  
The maximum number of constraint counts

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetMethod
=========================

Specifies the type of algorithm to use when faceting a field

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetMethod</span> ( <span
class="methodparam"><span class="type">string</span> `$method`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Specifies the type of algorithm to use when faceting a field. This
method accepts optional field override.

### Parameters

`method`  
The method to use.

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetMinCount
===========================

Maps to facet.mincount

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetMinCount</span> ( <span
class="methodparam"><span class="type">int</span> `$mincount`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Sets the minimum counts for facet fields that should be included in the
response

### Parameters

`mincount`  
The minimum count

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetMissing
==========================

Maps to facet.missing

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetMissing</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Used to indicate that in addition to the Term-based constraints of a
facet field, a count of all matching results which have no value for the
field should be computed

### Parameters

`flag`  
**`TRUE`** turns this feature on. **`FALSE`** disables it.

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetOffset
=========================

Sets the offset into the list of constraints to allow for pagination

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetOffset</span> ( <span
class="methodparam"><span class="type">int</span> `$offset`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Sets the offset into the list of constraints to allow for pagination.

### Parameters

`offset`  
The offset

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetPrefix
=========================

Specifies a string prefix with which to limits the terms on which to
facet

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetPrefix</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Specifies a string prefix with which to limits the terms on which to
facet.

### Parameters

`prefix`  
The prefix string

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setFacetSort
=======================

Determines the ordering of the facet field constraints

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetSort</span> ( <span
class="methodparam"><span class="type">int</span> `$facetSort`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Determines the ordering of the facet field constraints

### Parameters

`facetSort`  
Use SolrQuery::FACET\_SORT\_INDEX for sorting by index order or
SolrQuery::FACET\_SORT\_COUNT for sorting by count.

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setGroup
===================

Enable/Disable result grouping (group parameter)

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroup</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

Enable/Disable result grouping (group parameter)

### Parameters

`value`  

### Return Values

### See Also

-   <span class="methodname">SolrQuery::getGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::setGroupCachePercent
===============================

Enables caching for result grouping

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupCachePercent</span> ( <span
class="methodparam"><span class="type">int</span> `$percent`</span> )

Setting this parameter to a number greater than 0 enables caching for
result grouping. Result Grouping executes two searches; this option
caches the second search. The server default value is 0. Testing has
shown that group caching only improves search time with Boolean,
wildcard, and fuzzy queries. For simple queries like term or "match all"
queries, group caching degrades performance. group.cache.percent
parameter

### Parameters

`percent`  

### Return Values

### Errors/Exceptions

Emits <span class="classname">SolrIllegalArgumentException</span> in
case of an invalid parameter was passed.

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>

SolrQuery::setGroupFacet
========================

Sets group.facet parameter

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupFacet</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

Determines whether to compute grouped facets for the field facets
specified in facet.field parameters. Grouped facets are computed based
on the first specified group.

### Parameters

`value`  

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::setGroupFormat
=========================

Sets the group format, result structure (group.format parameter)

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Sets the group.format parameter. If this parameter is set to simple, the
grouped documents are presented in a single flat list, and the start and
rows parameters affect the numbers of documents instead of groups.
Accepts: grouped/simple

### Parameters

`value`  

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::setGroupLimit
========================

Specifies the number of results to return for each group. The server
default value is 1

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

Specifies the number of results to return for each group. The server
default value is 1.

### Parameters

`value`  

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::setGroupMain
=======================

If true, the result of the first field grouping command is used as the
main result list in the response, using group.format=simple

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupMain</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

If true, the result of the first field grouping command is used as the
main result list in the response, using group.format=simple.

### Parameters

`value`  

### Return Values

### See Also

-   

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::setGroupNGroups
==========================

If true, Solr includes the number of groups that have matched the query
in the results

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupNGroups</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

If true, Solr includes the number of groups that have matched the query
in the results.

### Parameters

`value`  

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::setGroupOffset
=========================

Sets the group.offset parameter

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupOffset</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

Sets the group.offset parameter.

### Parameters

`value`  

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupTruncate</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::setGroupTruncate
===========================

If true, facet counts are based on the most relevant document of each
group matching the query

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupTruncate</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

If true, facet counts are based on the most relevant document of each
group matching the query. The server default value is false.
group.truncate parameter

### Parameters

`value`  

### Return Values

### See Also

-   <span class="methodname">SolrQuery::setGroup</span>
-   <span class="methodname">SolrQuery::addGroupField</span>
-   <span class="methodname">SolrQuery::addGroupFunction</span>
-   <span class="methodname">SolrQuery::addGroupQuery</span>
-   <span class="methodname">SolrQuery::addGroupSortField</span>
-   <span class="methodname">SolrQuery::setGroupFacet</span>
-   <span class="methodname">SolrQuery::setGroupOffset</span>
-   <span class="methodname">SolrQuery::setGroupLimit</span>
-   <span class="methodname">SolrQuery::setGroupMain</span>
-   <span class="methodname">SolrQuery::setGroupNGroups</span>
-   <span class="methodname">SolrQuery::setGroupFormat</span>
-   <span class="methodname">SolrQuery::setGroupCachePercent</span>

SolrQuery::setHighlight
=======================

Enables or disables highlighting

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlight</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

Setting it to **`TRUE`** enables highlighted snippets to be generated in
the query response.

Setting it to **`FALSE`** disables highlighting

### Parameters

`flag`  
Enable or disable highlighting

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightAlternateField
=====================================

Specifies the backup field to use

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightAlternateField</span> (
<span class="methodparam"><span class="type">string</span>
`$field`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

If a snippet cannot be generated because there were no matching terms,
one can specify a field to use as the backup or default summary

### Parameters

`field`  
The name of the backup field

`field_override`  
The name of the field we are overriding this setting for.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightFormatter
================================

Specify a formatter for the highlight output

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightFormatter</span> ( <span
class="methodparam"><span class="type">string</span> `$formatter`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Specify a formatter for the highlight output.

### Parameters

`formatter`  
Currently the only legal value is "simple"

`field_override`  
The name of the field.

SolrQuery::setHighlightFragmenter
=================================

Sets a text snippet generator for highlighted text

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightFragmenter</span> (
<span class="methodparam"><span class="type">string</span>
`$fragmenter`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

Specify a text snippet generator for highlighted text.

### Parameters

`fragmenter`  
The standard fragmenter is gap. Another option is regex, which tries to
create fragments that resembles a certain regular expression

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightFragsize
===============================

The size of fragments to consider for highlighting

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightFragsize</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Sets the size, in characters, of fragments to consider for highlighting.
"0" indicates that the whole field value should be used (no
fragmenting).

### Parameters

`size`  
The size, in characters, of fragments to consider for highlighting

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightHighlightMultiTerm
=========================================

Use SpanScorer to highlight phrase terms

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setHighlightHighlightMultiTerm</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
)

Use SpanScorer to highlight phrase terms only when they appear within
the query phrase in the document.

### Parameters

`flag`  
Whether or not to use SpanScorer to highlight phrase terms only when
they appear within the query phrase in the document.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightMaxAlternateFieldLength
==============================================

Sets the maximum number of characters of the field to return

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setHighlightMaxAlternateFieldLength</span>
( <span class="methodparam"><span class="type">int</span>
`$fieldLength`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

If SolrQuery::setHighlightAlternateField() was passed the value
**`TRUE`**, this parameter specifies the maximum number of characters of
the field to return

Any value less than or equal to 0 means unlimited.

### Parameters

`fieldLength`  
The length of the field

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightMaxAnalyzedChars
=======================================

Specifies the number of characters into a document to look for suitable
snippets

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightMaxAnalyzedChars</span>
( <span class="methodparam"><span class="type">int</span>
`$value`</span> )

Specifies the number of characters into a document to look for suitable
snippets

### Parameters

`value`  
The number of characters into a document to look for suitable snippets

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightMergeContiguous
======================================

Whether or not to collapse contiguous fragments into a single fragment

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightMergeContiguous</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Whether or not to collapse contiguous fragments into a single fragment

### Parameters

`value`  
Whether or not to collapse contiguous fragments into a single fragment

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightRegexMaxAnalyzedChars
============================================

Specify the maximum number of characters to analyze

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setHighlightRegexMaxAnalyzedChars</span> (
<span class="methodparam"><span class="type">int</span>
`$maxAnalyzedChars`</span> )

Specify the maximum number of characters to analyze from a field when
using the regex fragmenter

### Parameters

`maxAnalyzedChars`  
The maximum number of characters to analyze from a field when using the
regex fragmenter

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightRegexPattern
===================================

Specify the regular expression for fragmenting

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightRegexPattern</span> (
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

Specifies the regular expression for fragmenting. This could be used to
extract sentences

### Parameters

`value`  
The regular expression for fragmenting. This could be used to extract
sentences

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightRegexSlop
================================

Sets the factor by which the regex fragmenter can stray from the ideal
fragment size

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightRegexSlop</span> ( <span
class="methodparam"><span class="type">float</span> `$factor`</span> )

The factor by which the regex fragmenter can stray from the ideal
fragment size ( specfied by SolrQuery::setHighlightFragsize )to
accommodate the regular expression

### Parameters

`factor`  
The factor by which the regex fragmenter can stray from the ideal
fragment size

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightRequireFieldMatch
========================================

Require field matching during highlighting

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightRequireFieldMatch</span>
( <span class="methodparam"><span class="type">bool</span>
`$flag`</span> )

If **`TRUE`**, then a field will only be highlighted if the query
matched in this particular field.

This will only work if SolrQuery::setHighlightUsePhraseHighlighter() was
set to **`TRUE`**

### Parameters

`flag`  
**`TRUE`** or **`FALSE`**

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightSimplePost
=================================

Sets the text which appears after a highlighted term

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightSimplePost</span> (
<span class="methodparam"><span class="type">string</span>
`$simplePost`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

Sets the text which appears before a highlighted term

### Parameters

`simplePost`  
Sets the text which appears after a highlighted term

``` parameters
The default is </em>
```

`field_override`  
The name of the field.

SolrQuery::setHighlightSimplePre
================================

Sets the text which appears before a highlighted term

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightSimplePre</span> ( <span
class="methodparam"><span class="type">string</span> `$simplePre`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Sets the text which appears before a highlighted term

``` description
The default is <em>
```

### Parameters

`simplePre`  
The text which appears before a highlighted term

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightSnippets
===============================

Sets the maximum number of highlighted snippets to generate per field

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightSnippets</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

Sets the maximum number of highlighted snippets to generate per field

### Parameters

`value`  
The maximum number of highlighted snippets to generate per field

`field_override`  
The name of the field.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setHighlightUsePhraseHighlighter
===========================================

Whether to highlight phrase terms only when they appear within the query
phrase

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setHighlightUsePhraseHighlighter</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
)

Sets whether or not to use SpanScorer to highlight phrase terms only
when they appear within the query phrase in the document

### Parameters

`value`  
Whether or not to use SpanScorer to highlight phrase terms only when
they appear within the query phrase in the document

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setMlt
=================

Enables or disables moreLikeThis

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMlt</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

Enables or disables moreLikeThis

### Parameters

`flag`  
**`TRUE`** enables it and **`FALSE`** turns it off.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setMltBoost
======================

Set if the query will be boosted by the interesting term relevance

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltBoost</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

Set if the query will be boosted by the interesting term relevance

### Parameters

`value`  
Sets to **`TRUE`** or **`FALSE`**

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setMltCount
======================

Set the number of similar documents to return for each result

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltCount</span> ( <span
class="methodparam"><span class="type">int</span> `$count`</span> )

Set the number of similar documents to return for each result

### Parameters

`count`  
The number of similar documents to return for each result

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setMltMaxNumQueryTerms
=================================

Sets the maximum number of query terms included

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMaxNumQueryTerms</span> (
<span class="methodparam"><span class="type">int</span> `$value`</span>
)

Sets the maximum number of query terms that will be included in any
generated query.

### Parameters

`value`  
The maximum number of query terms that will be included in any generated
query

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setMltMaxNumTokens
=============================

Specifies the maximum number of tokens to parse

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMaxNumTokens</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

Specifies the maximum number of tokens to parse in each example doc
field that is not stored with TermVector support.

### Parameters

`value`  
The maximum number of tokens to parse

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setMltMaxWordLength
==============================

Sets the maximum word length

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMaxWordLength</span> ( <span
class="methodparam"><span class="type">int</span>
`$maxWordLength`</span> )

Sets the maximum word length above which words will be ignored.

### Parameters

`maxWordLength`  
The maximum word length above which words will be ignored

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setMltMinDocFrequency
================================

Sets the mltMinDoc frequency

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMinDocFrequency</span> ( <span
class="methodparam"><span class="type">int</span>
`$minDocFrequency`</span> )

The frequency at which words will be ignored which do not occur in at
least this many docs.

### Parameters

`minDocFrequency`  
Sets the frequency at which words will be ignored which do not occur in
at least this many docs.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setMltMinTermFrequency
=================================

Sets the frequency below which terms will be ignored in the source docs

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMinTermFrequency</span> (
<span class="methodparam"><span class="type">int</span>
`$minTermFrequency`</span> )

Sets the frequency below which terms will be ignored in the source docs

### Parameters

`minTermFrequency`  
The frequency below which terms will be ignored in the source docs

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setMltMinWordLength
==============================

Sets the minimum word length

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMinWordLength</span> ( <span
class="methodparam"><span class="type">int</span>
`$minWordLength`</span> )

Sets the minimum word length below which words will be ignored.

### Parameters

`minWordLength`  
The minimum word length below which words will be ignored

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setOmitHeader
========================

Exclude the header from the returned results

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setOmitHeader</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

Exclude the header from the returned results.

### Parameters

`flag`  
**`TRUE`** excludes the header from the result.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setQuery
===================

Sets the search query

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

Sets the search query.

### Parameters

`query`  
The search query

### Return Values

Returns the current SolrQuery object

SolrQuery::setRows
==================

Specifies the maximum number of rows to return in the result

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setRows</span> ( <span
class="methodparam"><span class="type">int</span> `$rows`</span> )

Specifies the maximum number of rows to return in the result

### Parameters

`rows`  
The maximum number of rows to return

### Return Values

Returns the current SolrQuery object.

SolrQuery::setShowDebugInfo
===========================

Flag to show debug information

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setShowDebugInfo</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

Whether to show debug info

### Parameters

`flag`  
Whether to show debug info. **`TRUE`** or **`FALSE`**

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setStart
===================

Specifies the number of rows to skip

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setStart</span> ( <span
class="methodparam"><span class="type">int</span> `$start`</span> )

Specifies the number of rows to skip. Useful in pagination of results.

### Parameters

`start`  
The number of rows to skip.

### Return Values

Returns the current SolrQuery object.

SolrQuery::setStats
===================

Enables or disables the Stats component

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setStats</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

Enables or disables the Stats component.

### Parameters

`flag`  
**`TRUE`** turns on the stats component and **`FALSE`** disables it.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTerms
===================

Enables or disables the TermsComponent

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTerms</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

Enables or disables the TermsComponent

### Parameters

`flag`  
**`TRUE`** enables it. **`FALSE`** turns it off

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsField
========================

Sets the name of the field to get the Terms from

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldname`</span>
)

Sets the name of the field to get the terms from

### Parameters

`fieldname`  
The field name

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsIncludeLowerBound
====================================

Include the lower bound term in the result set

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsIncludeLowerBound</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
)

Include the lower bound term in the result set.

### Parameters

`flag`  
Include the lower bound term in the result set

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsIncludeUpperBound
====================================

Include the upper bound term in the result set

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsIncludeUpperBound</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
)

Include the upper bound term in the result set.

### Parameters

`flag`  
**`TRUE`** or **`FALSE`**

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsLimit
========================

Sets the maximum number of terms to return

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$limit`</span> )

Sets the maximum number of terms to return

### Parameters

`limit`  
The maximum number of terms to return. All the terms will be returned if
the limit is negative.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsLowerBound
=============================

Specifies the Term to start from

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsLowerBound</span> ( <span
class="methodparam"><span class="type">string</span>
`$lowerBound`</span> )

Specifies the Term to start from

### Parameters

`lowerBound`  
The lower bound Term

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsMaxCount
===========================

Sets the maximum document frequency

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsMaxCount</span> ( <span
class="methodparam"><span class="type">int</span> `$frequency`</span> )

Sets the maximum document frequency.

### Parameters

`frequency`  
The maximum document frequency.

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsMinCount
===========================

Sets the minimum document frequency

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsMinCount</span> ( <span
class="methodparam"><span class="type">int</span> `$frequency`</span> )

Sets the minimum doc frequency to return in order to be included

### Parameters

`frequency`  
The minimum frequency

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsPrefix
=========================

Restrict matches to terms that start with the prefix

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsPrefix</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span> )

Restrict matches to terms that start with the prefix

### Parameters

`prefix`  
Restrict matches to terms that start with the prefix

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsReturnRaw
============================

Return the raw characters of the indexed term

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsReturnRaw</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

If true, return the raw characters of the indexed term, regardless of if
it is human readable

### Parameters

`value`  
**`TRUE`** or **`FALSE`**

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsSort
=======================

Specifies how to sort the returned terms

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsSort</span> ( <span
class="methodparam"><span class="type">int</span> `$sortType`</span> )

If SolrQuery::TERMS\_SORT\_COUNT, sorts the terms by the term frequency
(highest count first). If SolrQuery::TERMS\_SORT\_INDEX, returns the
terms in index order

### Parameters

`sortType`  
SolrQuery::TERMS\_SORT\_INDEX or SolrQuery::TERMS\_SORT\_COUNT

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTermsUpperBound
=============================

Sets the term to stop at

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsUpperBound</span> ( <span
class="methodparam"><span class="type">string</span>
`$upperBound`</span> )

Sets the term to stop at

### Parameters

`upperBound`  
The term to stop at

### Return Values

Returns the current SolrQuery object, if the return value is used.

SolrQuery::setTimeAllowed
=========================

The time allowed for search to finish

### Description

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTimeAllowed</span> ( <span
class="methodparam"><span class="type">int</span> `$timeAllowed`</span>
)

The time allowed for a search to finish. This value only applies to the
search and not to requests in general. Time is in milliseconds. Values
less than or equal to zero implies no time restriction. Partial results
may be returned, if there are any.

### Parameters

`timeAllowed`  
The time allowed for a search to finish.

### Return Values

Returns the current SolrQuery object, if the return value is used.

Introduction
------------

Class synopsis
--------------

**SolrDisMaxQuery**

<span class="ooclass"> class **SolrDisMaxQuery** </span> <span
class="ooclass"> <span class="modifier">extends</span> **SolrQuery**
</span> <span class="oointerface">implements <span
class="interfacename">Serializable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::ORDER_ASC` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::ORDER_DESC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::FACET_SORT_INDEX` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::FACET_SORT_COUNT` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::TERMS_SORT_INDEX` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SolrQuery::TERMS_SORT_COUNT` <span class="initializer"> = 1</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">addBigramPhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">string</span>
`$boost`</span> \[, <span class="methodparam"><span
class="type">string</span> `$slop`</span> \] )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">addBoostQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">string</span> `$boost`</span> \] )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">addPhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">string</span>
`$boost`</span> \[, <span class="methodparam"><span
class="type">string</span> `$slop`</span> \] )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">addQueryField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$boost`</span> \] )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">addTrigramPhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">string</span>
`$boost`</span> \[, <span class="methodparam"><span
class="type">string</span> `$slop`</span> \] )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">addUserField</span> ( <span class="methodparam"><span
class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$q`</span> \] )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">removeBigramPhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">removeBoostQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">removePhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">removeQueryField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">removeTrigramPhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">removeUserField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setBigramPhraseFields</span> ( <span
class="methodparam"><span class="type">string</span> `$fields`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setBigramPhraseSlop</span> ( <span
class="methodparam"><span class="type">string</span> `$slop`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setBoostFunction</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setBoostQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$q`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setMinimumMatch</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setPhraseFields</span> ( <span
class="methodparam"><span class="type">string</span> `$fields`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setPhraseSlop</span> ( <span
class="methodparam"><span class="type">string</span> `$slop`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setQueryAlt</span> ( <span class="methodparam"><span
class="type">string</span> `$q`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setQueryPhraseSlop</span> ( <span
class="methodparam"><span class="type">string</span> `$slop`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setTieBreaker</span> ( <span
class="methodparam"><span class="type">string</span>
`$tieBreaker`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setTrigramPhraseFields</span> ( <span
class="methodparam"><span class="type">string</span> `$fields`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setTrigramPhraseSlop</span> ( <span
class="methodparam"><span class="type">string</span> `$slop`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">setUserFields</span> ( <span
class="methodparam"><span class="type">string</span> `$fields`</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">useDisMaxQueryParser</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">useEDisMaxQueryParser</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addExpandFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addExpandSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$order`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFacetDateField</span> ( <span
class="methodparam"><span class="type">string</span> `$dateField`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFacetDateOther</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFacetField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFacetQuery</span> ( <span
class="methodparam"><span class="type">string</span>
`$facetQuery`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addGroupField</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addGroupFunction</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addGroupQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addGroupSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">int</span> `$order`</span>
\] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addHighlightField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addMltField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addMltQueryField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">float</span>
`$boost`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">int</span> `$order`<span
class="initializer"> = SolrQuery::ORDER\_DESC</span></span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addStatsFacet</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::addStatsField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::collapse</span> ( <span
class="methodparam"><span class="type">SolrCollapseFunction</span>
`$collapseFunction`</span> )

<span class="modifier">public</span> <span
class="methodname">SolrQuery::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$q`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SolrQuery::\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getExpand</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getExpandFilterQueries</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getExpandQuery</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getExpandRows</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getExpandSortFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getFacet</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetDateEnd</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFacetDateFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetDateGap</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetDateHardEnd</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFacetDateOther</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetDateStart</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFacetFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getFacetLimit</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetMethod</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getFacetMinCount</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getFacetMissing</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getFacetOffset</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getFacetPrefix</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFacetQueries</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getFacetSort</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getFilterQueries</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroup</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getGroupCachePercent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroupFacet</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getGroupFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getGroupFormat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getGroupFunctions</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getGroupLimit</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroupMain</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroupNGroups</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getGroupOffset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getGroupQueries</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getGroupSortFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getGroupTruncate</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getHighlight</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightAlternateField</span>
(\[ <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getHighlightFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightFormatter</span> (\[
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightFragmenter</span> (\[
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightFragsize</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">SolrQuery::getHighlightHighlightMultiTerm</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightMaxAlternateFieldLength</span>
(\[ <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightMaxAnalyzedChars</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getHighlightMergeContiguous</span>
(\[ <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightRegexMaxAnalyzedChars</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightRegexPattern</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">SolrQuery::getHighlightRegexSlop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getHighlightRequireFieldMatch</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightSimplePost</span> (\[
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getHighlightSimplePre</span> (\[
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getHighlightSnippets</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">SolrQuery::getHighlightUsePhraseHighlighter</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getMlt</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getMltBoost</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getMltFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMaxNumQueryTerms</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMaxNumTokens</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMaxWordLength</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMinDocFrequency</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMinTermFrequency</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getMltMinWordLength</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getMltQueryFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getQuery</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getRows</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getSortFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getStart</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getStats</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getStatsFacets</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrQuery::getStatsFields</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getTerms</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getTermsField</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getTermsIncludeLowerBound</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getTermsIncludeUpperBound</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTermsLimit</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getTermsLowerBound</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTermsMaxCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTermsMinCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getTermsPrefix</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SolrQuery::getTermsReturnRaw</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTermsSort</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrQuery::getTermsUpperBound</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrQuery::getTimeAllowed</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeExpandFilterQuery</span> (
<span class="methodparam"><span class="type">string</span> `$fq`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeExpandSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFacetDateField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFacetDateOther</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFacetField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFacetQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeFilterQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$fq`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeHighlightField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeMltField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeMltQueryField</span> ( <span
class="methodparam"><span class="type">string</span>
`$queryField`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeSortField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeStatsFacet</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::removeStatsField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setEchoHandler</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setEchoParams</span> ( <span
class="methodparam"><span class="type">string</span> `$type`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setExpand</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setExpandQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$q`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setExpandRows</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setExplainOther</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacet</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetDateEnd</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetDateGap</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetDateHardEnd</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetDateStart</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setFacetEnumCacheMinDefaultFrequency</span>
( <span class="methodparam"><span class="type">int</span>
`$frequency`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$limit`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetMethod</span> ( <span
class="methodparam"><span class="type">string</span> `$method`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetMinCount</span> ( <span
class="methodparam"><span class="type">int</span> `$mincount`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetMissing</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetOffset</span> ( <span
class="methodparam"><span class="type">int</span> `$offset`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetPrefix</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setFacetSort</span> ( <span
class="methodparam"><span class="type">int</span> `$facetSort`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroup</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupCachePercent</span> ( <span
class="methodparam"><span class="type">int</span> `$percent`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupFacet</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupMain</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupNGroups</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupOffset</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setGroupTruncate</span> ( <span
class="methodparam"><span class="type">bool</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlight</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightAlternateField</span> (
<span class="methodparam"><span class="type">string</span>
`$field`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightFormatter</span> ( <span
class="methodparam"><span class="type">string</span> `$formatter`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightFragmenter</span> (
<span class="methodparam"><span class="type">string</span>
`$fragmenter`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightFragsize</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setHighlightHighlightMultiTerm</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setHighlightMaxAlternateFieldLength</span>
( <span class="methodparam"><span class="type">int</span>
`$fieldLength`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightMaxAnalyzedChars</span>
( <span class="methodparam"><span class="type">int</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightMergeContiguous</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setHighlightRegexMaxAnalyzedChars</span> (
<span class="methodparam"><span class="type">int</span>
`$maxAnalyzedChars`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightRegexPattern</span> (
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightRegexSlop</span> ( <span
class="methodparam"><span class="type">float</span> `$factor`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightRequireFieldMatch</span>
( <span class="methodparam"><span class="type">bool</span>
`$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightSimplePost</span> (
<span class="methodparam"><span class="type">string</span>
`$simplePost`</span> \[, <span class="methodparam"><span
class="type">string</span> `$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightSimplePre</span> ( <span
class="methodparam"><span class="type">string</span> `$simplePre`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setHighlightSnippets</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$field_override`</span> \] )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span
class="methodname">SolrQuery::setHighlightUsePhraseHighlighter</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMlt</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltBoost</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltCount</span> ( <span
class="methodparam"><span class="type">int</span> `$count`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMaxNumQueryTerms</span> (
<span class="methodparam"><span class="type">int</span> `$value`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMaxNumTokens</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMaxWordLength</span> ( <span
class="methodparam"><span class="type">int</span>
`$maxWordLength`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMinDocFrequency</span> ( <span
class="methodparam"><span class="type">int</span>
`$minDocFrequency`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMinTermFrequency</span> (
<span class="methodparam"><span class="type">int</span>
`$minTermFrequency`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setMltMinWordLength</span> ( <span
class="methodparam"><span class="type">int</span>
`$minWordLength`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setOmitHeader</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setRows</span> ( <span
class="methodparam"><span class="type">int</span> `$rows`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setShowDebugInfo</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setStart</span> ( <span
class="methodparam"><span class="type">int</span> `$start`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setStats</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTerms</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldname`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsIncludeLowerBound</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsIncludeUpperBound</span> (
<span class="methodparam"><span class="type">bool</span> `$flag`</span>
)

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$limit`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsLowerBound</span> ( <span
class="methodparam"><span class="type">string</span>
`$lowerBound`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsMaxCount</span> ( <span
class="methodparam"><span class="type">int</span> `$frequency`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsMinCount</span> ( <span
class="methodparam"><span class="type">int</span> `$frequency`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsPrefix</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsReturnRaw</span> ( <span
class="methodparam"><span class="type">bool</span> `$flag`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsSort</span> ( <span
class="methodparam"><span class="type">int</span> `$sortType`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTermsUpperBound</span> ( <span
class="methodparam"><span class="type">string</span>
`$upperBound`</span> )

<span class="modifier">public</span> <span class="type">SolrQuery</span>
<span class="methodname">SolrQuery::setTimeAllowed</span> ( <span
class="methodparam"><span class="type">int</span> `$timeAllowed`</span>
)

}

Predefined Constants
--------------------

**`SolrDisMaxQuery::ORDER_ASC`**  
Used to specify that the sorting should be in acending order (Duplicated
for easier migration)

**`SolrDisMaxQuery::ORDER_DESC`**  
Used to specify that the sorting should be in descending order
(Duplicated for easier migration)

**`SolrDisMaxQuery::FACET_SORT_INDEX`**  
Used to specify that the facet should sort by index (Duplicated for
easier migration)

**`SolrDisMaxQuery::FACET_SORT_COUNT`**  
Used to specify that the facet should sort by count (Duplicated for
easier migration)

**`SolrDisMaxQuery::TERMS_SORT_INDEX`**  
Used in the TermsComponent (Duplicated for easier migration)

**`SolrDisMaxQuery::TERMS_SORT_COUNT`**  
Used in the TermsComponent (Duplicated for easier migration)

SolrDisMaxQuery::addBigramPhraseField
=====================================

Adds a Phrase Bigram Field (pf2 parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::addBigramPhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">string</span>
`$boost`</span> \[, <span class="methodparam"><span
class="type">string</span> `$slop`</span> \] )

Adds a Phrase Bigram Field (pf2 parameter) output format:
field\~slop^boost OR field^boost Slop is optional

### Parameters

`field`  

`boost`  

`slop`  

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::addBigramPhraseField</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery("lucene");
$dismaxQuery
    ->addBigramPhraseField('cat', 2, 5.1)
    ->addBigramPhraseField('feature', 4.5)
;
echo $dismaxQuery;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&pf2=cat~5.1^2 feature^4.5

### See Also

-   <span
    class="methodname">SolrDisMaxQuery::removeBigramPhraseField</span>
-   <span
    class="methodname">SolrDisMaxQuery::setBigramPhraseFields</span>
-   <span class="methodname">SolrDisMaxQuery::setBigramPhraseSlop</span>

SolrDisMaxQuery::addBoostQuery
==============================

Adds a boost query field with value and optional boost (bq parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::addBoostQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">string</span> `$boost`</span> \] )

Adds a Boost Query field with value \[and boost\] (bq parameter)

### Parameters

`field`  

`value`  

`boost`  

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::addBoostQuery</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery("lucene");
$dismaxQuery
    ->addBoostQuery('cat', 'clothing', 2)
    ->addBoostQuery('cat', 'electronics', 5.1)
;
echo $dismaxQuery.PHP_EOL;
?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&bq=cat:clothing^2 cat:electronics^5.1

### See Also

-   <span class="methodname">SolrDisMaxQuery::removeBoostQuery</span>
-   <span class="methodname">SolrDisMaxQuery::setBoostQuery</span>

SolrDisMaxQuery::addPhraseField
===============================

Adds a Phrase Field (pf parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::addPhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">string</span>
`$boost`</span> \[, <span class="methodparam"><span
class="type">string</span> `$slop`</span> \] )

Adds a Phrase Field (pf parameter)

### Parameters

`field`  
field name

`boost`  

`slop`  

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::addPhraseField</span> example**

``` php
<?php
$dismaxQuery = new SolrDisMaxQuery("lucene");
$dismaxQuery
    ->addPhraseField('cat', 3, 1)
    ->addPhraseField('third', 4, 2)
    ->addPhraseField('source', 55)
;
echo $dismaxQuery;
?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&pf=cat~1^3 third~2^4 source^55

### See Also

-   <span class="methodname">SolrDisMaxQuery::removePhraseField</span>
-   <span class="methodname">SolrDisMaxQuery::setPhraseFields</span>

SolrDisMaxQuery::addQueryField
==============================

Add a query field with optional boost (qf parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::addQueryField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$boost`</span> \] )

Add a query field with optional boost (qf parameter)

### Parameters

`field`  
field name

`boost`  
Boost value. Boosts documents with matching terms.

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::addQueryField</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery("lucene");
$dismaxQuery
    ->addQueryField("location", 4)
    ->addQueryField("price")
    ->addQueryField("sku")
    ->addQueryField("title",3.4)
;
echo $dismaxQuery;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&qf=location^4 price sku title^3.4

### See Also

-   <span class="methodname">SolrDisMaxQuery::removeQueryField</span>

SolrDisMaxQuery::addTrigramPhraseField
======================================

Adds a Trigram Phrase Field (pf3 parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::addTrigramPhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> ,
<span class="methodparam"><span class="type">string</span>
`$boost`</span> \[, <span class="methodparam"><span
class="type">string</span> `$slop`</span> \] )

Adds a Trigram Phrase Field (pf3 parameter)

### Parameters

`field`  
Field Name

`boost`  
Field Boost

`slop`  
Field Slop

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::addTrigramPhraseField</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');
$dismaxQuery
->addTrigramPhraseField('cat', 2, 5.1)
->addTrigramPhraseField('feature', 4.5)
;
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output:

    q=lucene&defType=%s&pf3=cat~5.1^2 feature^4.5

### See Also

-   <span
    class="methodname">SolrDisMaxQuery::removeTrigramPhraseField</span>
-   <span
    class="methodname">SolrDisMaxQuery::setTrigramPhraseFields</span>
-   <span
    class="methodname">SolrDisMaxQuery::setTrigramPhraseSlop</span>

SolrDisMaxQuery::addUserField
=============================

Adds a field to User Fields Parameter (uf)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::addUserField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Adds a field to The User Fields Parameter (uf)

### Parameters

`field`  
Field Name

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::addUserField</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');
$dismaxQuery
->addUserField('cat')
->addUserField('text')
->addUserField('*_dt');

echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&uf=cat text *_dt

### See Also

-   <span class="methodname">SolrDisMaxQuery::removeUserField</span>
-   <span class="methodname">SolrDisMaxQuery::setUserFields</span>

SolrDisMaxQuery::\_\_construct
==============================

Class Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrDisMaxQuery::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$q`</span> \] )

Class constructor initializes the object and sets the q parameter if
passed

### Parameters

`q`  
Search Query (q parameter)

### Return Values

### Errors/Exceptions

Emits <span class="classname">SolrIllegalArgumentException</span> in
case of an invalid parameter was passed.

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::\_\_construct</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');
echo $dismaxQuery;

?>
```

The above example will output:

    q=lucene&defType=edismax

### See Also

-   

SolrDisMaxQuery::removeBigramPhraseField
========================================

Removes phrase bigram field (pf2 parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::removeBigramPhraseField</span> (
<span class="methodparam"><span class="type">string</span>
`$field`</span> )

Removes a Bigram Phrase Field (pf2 parameter) that was previously added
using <span
class="methodname">SolrDisMaxQuery::addBigramPhraseField</span>

### Parameters

`field`  
The Field Name

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::removeBigramPhraseField</span>
example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery("lucene");
$dismaxQuery
    ->addBigramPhraseField('cat', 2, 5.1)
    ->addBigramPhraseField('feature', 4.5)
;
echo $dismaxQuery.PHP_EOL;

// remove cat from pf2
$dismaxQuery
    ->removeBigramPhraseField('cat');
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&pf2=cat~5.1^2 feature^4.5
    q=lucene&defType=edismax&pf2=feature^4.5

### See Also

-   <span
    class="methodname">SolrDisMaxQuery::addBigramPhraseField</span>
-   <span
    class="methodname">SolrDisMaxQuery::setBigramPhraseFields</span>
-   <span class="methodname">SolrDisMaxQuery::setBigramPhraseSlop</span>

SolrDisMaxQuery::removeBoostQuery
=================================

Removes a boost query partial by field name (bq)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::removeBoostQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes a boost query partial from the existing query, only if <span
class="methodname">SolrDisMaxQuery::addBoostQuery</span> was used.

### Parameters

`field`  
Field Name

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::removeBoostQuery</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery("lucene");
$dismaxQuery
    ->addBoostQuery('cat', 'electronics', 5.1)
    ->addBoostQuery('cat', 'hard drive')
;
echo $dismaxQuery.PHP_EOL;
// now remove a query part with field 'cat'
$dismaxQuery
->removeBoostQuery('cat');
echo $dismaxQuery . PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&bq=cat:electronics^5.1 cat:hard drive
    q=lucene&defType=edismax&bq=cat:hard drive

### See Also

-   <span class="methodname">SolrDisMaxQuery::addBoostQuery</span>
-   <span class="methodname">SolrDisMaxQuery::setBoostQuery</span>

SolrDisMaxQuery::removePhraseField
==================================

Removes a Phrase Field (pf parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::removePhraseField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes a Phrase Field (pf parameter) that was previously added using
SolrDisMaxQuery::addPhraseField

### Parameters

`field`  
Field Name

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::removePhraseField</span> example**

``` php
<?php
$dismaxQuery = new SolrDisMaxQuery('lucene');
$dismaxQuery
    ->addPhraseField('first', 3, 1)
    ->addPhraseField('second', 4, 1)
    ->addPhraseField('cat', 55);
echo $dismaxQuery . PHP_EOL;
echo $dismaxQuery->removePhraseField('second');
?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&pf=first~1^3 second~1^4 cat^55
    q=lucene&defType=edismax&pf=first~1^3 cat^55

### See Also

-   <span class="methodname">SolrDisMaxQuery::addPhraseField</span>
-   <span class="methodname">SolrDisMaxQuery::setPhraseFields</span>

SolrDisMaxQuery::removeQueryField
=================================

Removes a Query Field (qf parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::removeQueryField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes a Query Field (qf parameter) from the field list added by <span
class="methodname">SolrDisMaxQuery::addQueryField</span>

qf: When building DisjunctionMaxQueries from the user's query it
specifies the fields to search in, and boosts for those fields.

### Parameters

`field`  
Field Name

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::removeQueryField</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');
$dismaxQuery
    ->addQueryField('first', 3)
    ->addQueryField('second', 0.2)
    ->addQueryField('cat');
echo $dismaxQuery . PHP_EOL;
// remove field 'second'
echo $dismaxQuery->removeQueryField('second');
?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&qf=first^3 second^0.2 cat
    q=lucene&defType=edismax&qf=first^3 cat

### See Also

-   <span class="methodname">SolrDisMaxQuery::addQueryField</span>

SolrDisMaxQuery::removeTrigramPhraseField
=========================================

Removes a Trigram Phrase Field (pf3 parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::removeTrigramPhraseField</span> (
<span class="methodparam"><span class="type">string</span>
`$field`</span> )

Removes a Trigram Phrase Field (pf3 parameter)

### Parameters

`field`  
Field Name

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::removeTrigramPhraseField</span>
example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');
$dismaxQuery
->addTrigramPhraseField('cat', 2, 5.1)
->addTrigramPhraseField('feature', 4.5)
;
echo $dismaxQuery.PHP_EOL;
// reverse
$dismaxQuery
->removeTrigramPhraseField('cat');
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output:

    q=lucene&defType=%s&pf3=cat~5.1^2 feature^4.5
    q=lucene&defType=%s&pf3=feature^4.5

### See Also

-   <span
    class="methodname">SolrDisMaxQuery::addTrigramPhraseField</span>
-   <span
    class="methodname">SolrDisMaxQuery::setTrigramPhraseFields</span>
-   <span
    class="methodname">SolrDisMaxQuery::setTrigramPhraseSlop</span>

SolrDisMaxQuery::removeUserField
================================

Removes a field from The User Fields Parameter (uf)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::removeUserField</span> ( <span
class="methodparam"><span class="type">string</span> `$field`</span> )

Removes a field from The User Fields Parameter (uf)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`field`  
Field Name

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::removeUserField</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');
$dismaxQuery
->addUserField('cat')
->addUserField('text')
->addUserField('*_dt')
;
echo $dismaxQuery.PHP_EOL;

// remove field named 'text'
$dismaxQuery
->removeUserField('text');
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=%s&uf=cat text *_dt
    q=lucene&defType=%s&uf=cat *_dt

### See Also

-   <span class="methodname">SolrDisMaxQuery::addUserField</span>
-   <span class="methodname">SolrDisMaxQuery::setUserFields</span>

SolrDisMaxQuery::setBigramPhraseFields
======================================

Sets Bigram Phrase Fields and their boosts (and slops) using pf2
parameter

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setBigramPhraseFields</span> ( <span
class="methodparam"><span class="type">string</span> `$fields`</span> )

Sets Bigram Phrase Fields (pf2) and their boosts (and slops)

### Parameters

`fields`  
Fields boosts (slops)

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setBigramPhraseFields</span> example**

``` php
<?php
$dismaxQuery = new SolrDisMaxQuery("lucene");
$dismaxQuery->setBigramPhraseFields("cat~5.1^2 feature^4.5");
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&pf2=cat~5.1^2 feature^4.5

### See Also

-   <span class="methodname">SolrDisMaxQuery::setBigramPhraseSlop</span>
-   <span
    class="methodname">SolrDisMaxQuery::addBigramPhraseFields</span>
-   <span
    class="methodname">SolrDisMaxQuery::removeBigramPhraseField</span>
-   <span
    class="methodname">SolrDisMaxQuery::setTrigramPhraseFields</span>

SolrDisMaxQuery::setBigramPhraseSlop
====================================

Sets Bigram Phrase Slop (ps2 parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setBigramPhraseSlop</span> ( <span
class="methodparam"><span class="type">string</span> `$slop`</span> )

Sets Bigram Phrase Slop (ps2 parameter). A default slop for Bigram
phrase fields.

### Parameters

`slop`  

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setBigramPhraseSlop</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');

$dismaxQuery->setBigramPhraseSlop(5);
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&ps2=5

### See Also

-   

SolrDisMaxQuery::setBoostFunction
=================================

Sets a Boost Function (bf parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setBoostFunction</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

Sets Boost Function (bf parameter).

Functions (with optional boosts) that will be included in the user's
query to influence the score. Any function supported natively by Solr
can be used, along with a boost value. e.g.:

recip(rord(myfield),1,2,3)^1.5

### Parameters

`function`  

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setBoostFunction</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');

$boostRecentDocsFunction = "recip(ms(NOW,mydatefield),3.16e-11,1,1)";
$dismaxQuery->setBoostFunction($boostRecentDocsFunction);

echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&bf=recip(ms(NOW,mydatefield),3.16e-11,1,1)

### See Also

-   

SolrDisMaxQuery::setBoostQuery
==============================

Directly Sets Boost Query Parameter (bq)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setBoostQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$q`</span> )

Sets Boost Query Parameter (bq)

### Parameters

`q`  
query

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setBoostQuery</span> example**

``` php
<?php
$dismaxQuery = new SolrDisMaxQuery("lucene");

$dismaxQuery->setBoostQuery('cat:electronics manu:local^2');
echo $dismaxQuery.PHP_EOL;
?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&bq=cat:electronics manu:local^2

### See Also

-   <span class="methodname">SolrDisMaxQuery::addBoostQuery</span>
-   <span class="methodname">SolrDisMaxQuery::removeBoostQuery</span>

SolrDisMaxQuery::setMinimumMatch
================================

Set Minimum "Should" Match (mm)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setMinimumMatch</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Set Minimum "Should" Match parameter (mm). If the default query operator
is AND then mm=100%, if the default query operator (q.op) is OR, then
mm=0%.

### Parameters

`value`  
Minimum match value/expression

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setMinimumMatch</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery("lucene");
// 75% of the query clauses must match
$dismaxQuery->setMinimumMatch("75%");
echo $dismaxQuery . PHP_EOL;

?>
```

The above example will output:

    q=lucene&defType=edismax&mm=75%

SolrDisMaxQuery::setPhraseFields
================================

Sets Phrase Fields and their boosts (and slops) using pf2 parameter

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setPhraseFields</span> ( <span
class="methodparam"><span class="type">string</span> `$fields`</span> )

Sets Phrase Fields (pf) and their boosts (and slops)

### Parameters

`fields`  
Fields, boosts \[, slops\]

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setPhraseFields</span> example**

``` php
<?php
$dismaxQuery = new SolrDisMaxQuery("lucene");
$dismaxQuery->setPhraseFields("cat~5.1^2 feature^4.5");
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&pf=cat~5.1^2 feature^4.5

### See Also

-   <span class="methodname">SolrDisMaxQuery::addPhraseFields</span>
-   <span class="methodname">SolrDisMaxQuery::removePhraseField</span>

SolrDisMaxQuery::setPhraseSlop
==============================

Sets the default slop on phrase queries (ps parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setPhraseSlop</span> ( <span
class="methodparam"><span class="type">string</span> `$slop`</span> )

Sets the default amount of slop on phrase queries built with "pf", "pf2"
and/or "pf3" fields (affects boosting). "ps" parameter

### Parameters

`slop`  

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setPhraseSlop</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');

$dismaxQuery->setPhraseSlop(4);
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output:

    q=lucene&defType=edismax&ps=4

### See Also

-   

SolrDisMaxQuery::setQueryAlt
============================

Set Query Alternate (q.alt parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setQueryAlt</span> ( <span
class="methodparam"><span class="type">string</span> `$q`</span> )

Set Query Alternate (q.alt parameter)

When the main *q* parameter is not specified or is blank. The *q.alt*
parameter is used

### Parameters

`q`  
Query String

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span class="function">SolrDisMaxQuery::setQueryAlt</span>
example**

``` php
<?php

$dismaxQuery = new DisMaxQuery();
$dismaxQuery->setQueryAlt('*:*');

?>
```

The above example will output something similar to:

    defType=edismax&q.alt=*:*&q=

SolrDisMaxQuery::setQueryPhraseSlop
===================================

Specifies the amount of slop permitted on phrase queries explicitly
included in the user's query string (qf parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setQueryPhraseSlop</span> ( <span
class="methodparam"><span class="type">string</span> `$slop`</span> )

The Query Phrase Slop is the amount of slop permitted on phrase queries
explicitly included in the user's query string with the *qf* parameter.

slop refers to the number of positions one token needs to be moved in
relation to another token in order to match a phrase specified in a
query.

### Parameters

`slop`  
Amount of slop

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setQueryPhraseSlop</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery();
$dismaxQuery->setQueryPhraseSlop(3);
echo $dismaxQuery;
?>
```

The above example will output something similar to:

    defType=edismax&qs=3

SolrDisMaxQuery::setTieBreaker
==============================

Sets Tie Breaker parameter (tie parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setTieBreaker</span> ( <span
class="methodparam"><span class="type">string</span>
`$tieBreaker`</span> )

Sets Tie Breaker parameter (tie parameter)

### Parameters

`tieBreaker`  
The *tie* parameter specifies a float value (which should be something
much less than 1) to use as tiebreaker in DisMax queries.

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setTieBreaker</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery();
$dismaxQuery->setTieBreaker(0.1);

echo $dismaxQuery;

?>
```

The above example will output:

    defType=edismax&tie=0.1

SolrDisMaxQuery::setTrigramPhraseFields
=======================================

Directly Sets Trigram Phrase Fields (pf3 parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setTrigramPhraseFields</span> (
<span class="methodparam"><span class="type">string</span>
`$fields`</span> )

Directly Sets Trigram Phrase Fields (pf3 parameter)

### Parameters

`fields`  
Trigram Phrase Fields

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setTrigramPhraseFields</span>
example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');
$dismaxQuery->setTrigramPhraseFields('cat~5.1^2 feature^4.5');
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output:

    q=lucene&defType=edismax&pf3=cat~5.1^2 feature^4.5

### See Also

-   <span
    class="methodname">SolrDisMaxQuery::addTrigramPhraseField</span>
-   <span
    class="methodname">SolrDisMaxQuery::removeTrigramPhraseField</span>
-   <span
    class="methodname">SolrDisMaxQuery::setTrigramPhraseSlop</span>

SolrDisMaxQuery::setTrigramPhraseSlop
=====================================

Sets Trigram Phrase Slop (ps3 parameter)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setTrigramPhraseSlop</span> ( <span
class="methodparam"><span class="type">string</span> `$slop`</span> )

Sets Trigram Phrase Slop (ps3 parameter)

### Parameters

`slop`  
Phrase slop

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setTrigramPhraseSlop</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');
$dismaxQuery->setTrigramPhraseSlop(2);
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&ps3=2

### See Also

-   <span
    class="methodname">SolrDisMaxQuery::addTrigramPhraseField</span>
-   <span
    class="methodname">SolrDisMaxQuery::removeTrigramPhraseField</span>
-   <span
    class="methodname">SolrDisMaxQuery::setTrigramPhraseFields</span>

SolrDisMaxQuery::setUserFields
==============================

Sets User Fields parameter (uf)

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::setUserFields</span> ( <span
class="methodparam"><span class="type">string</span> `$fields`</span> )

Sets User Fields parameter (uf)

User Fields: Specifies which schema fields the end user shall be allowed
to query.

### Parameters

`fields`  
Fields names separated by space

This parameter supports wildcards.

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::setUserFields</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery('lucene');
$dismaxQuery->setUserFields('field1 field2 *_txt');
echo $dismaxQuery.PHP_EOL;

?>
```

The above example will output something similar to:

    q=lucene&defType=edismax&uf=field1 field2 *_txt

### See Also

-   <span class="methodname">SolrDisMaxQuery::addUserField</span>
-   <span class="methodname">SolrDisMaxQuery::removeUserField</span>

SolrDisMaxQuery::useDisMaxQueryParser
=====================================

Switch QueryParser to be DisMax Query Parser

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::useDisMaxQueryParser</span> ( <span
class="methodparam">void</span> )

Switch QueryParser to be DisMax Query Parser

### Parameters

This function has no parameters.

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::useDisMaxQueryParser</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery();
$dismaxQuery->useDisMaxQueryParser();
echo $dismaxQuery;
?>
```

The above example will output something similar to:

    defType=dismax

### See Also

-   <span
    class="methodname">SolrDisMaxQuery::useDisMaxQueryParser</span>

SolrDisMaxQuery::useEDisMaxQueryParser
======================================

Switch QueryParser to be EDisMax

### Description

<span class="modifier">public</span> <span
class="type">SolrDisMaxQuery</span> <span
class="methodname">SolrDisMaxQuery::useEDisMaxQueryParser</span> ( <span
class="methodparam">void</span> )

Switch QueryParser to be EDisMax. By default the query builder uses
edismax, if it was switched using <span
class="methodname">SolrDisMaxQuery::useDisMaxQueryParser</span>, it can
be switched back using this method.

### Parameters

This function has no parameters.

### Return Values

<span class="type">SolrDisMaxQuery</span>

### Examples

**Example \#1 <span
class="function">SolrDisMaxQuery::useEDisMaxQueryParser</span> example**

``` php
<?php

$dismaxQuery = new SolrDisMaxQuery();
$dismaxQuery->useEDisMaxQueryParser();
echo $dismaxQuery;

?>
```

The above example will output something similar to:

    defType=edismax

### See Also

-   

Introduction
------------

Class synopsis
--------------

**SolrCollapseFunction**

<span class="ooclass"> class **SolrCollapseFunction** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`SolrCollapseFunction::NULLPOLICY_IGNORE` <span class="initializer"> =
ignore</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`SolrCollapseFunction::NULLPOLICY_EXPAND` <span class="initializer"> =
expand</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`SolrCollapseFunction::NULLPOLICY_COLLAPSE` <span class="initializer"> =
collapse</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$field`</span> \]
)

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getField</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getHint</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getMax</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getMin</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getNullPolicy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">setField</span> ( <span class="methodparam"><span
class="type">string</span> `$fieldName`</span> )

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">setHint</span> ( <span class="methodparam"><span
class="type">string</span> `$hint`</span> )

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">setMax</span> ( <span class="methodparam"><span
class="type">string</span> `$max`</span> )

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">setMin</span> ( <span class="methodparam"><span
class="type">string</span> `$min`</span> )

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">setNullPolicy</span> ( <span
class="methodparam"><span class="type">string</span>
`$nullPolicy`</span> )

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">setSize</span> ( <span class="methodparam"><span
class="type">int</span> `$size`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`SolrCollapseFunction::NULLPOLICY_IGNORE`**  

**`SolrCollapseFunction::NULLPOLICY_EXPAND`**  

**`SolrCollapseFunction::NULLPOLICY_COLLAPSE`**  

SolrCollapseFunction::\_\_construct
===================================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">SolrCollapseFunction::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$field`</span> \]
)

Collapse Function constructor

### Parameters

`field`  
The field name to collapse on.

In order to collapse a result. The field type must be a single valued
String, Int or Float.

### Examples

**Example \#1 <span
class="function">SolrCollapseFunction::\_\_construct</span> example**

``` php
<?php

include "bootstrap.php";

$options = array
(
    'hostname' => SOLR_SERVER_HOSTNAME,
    'login'    => SOLR_SERVER_USERNAME,
    'password' => SOLR_SERVER_PASSWORD,
    'port'     => SOLR_SERVER_PORT,
    'path'     => SOLR_SERVER_PATH
);

$client = new SolrClient($options);

$query = new SolrQuery('*:*');

$func = new SolrCollapseFunction('field_name');

$func->setMax('sum(cscore(),field(some_other_field))');
$func->setSize(100);
$func->setNullPolicy(SolrCollapseFunction::NULLPOLICY_EXPAND);

$query->collapse($func);

$queryResponse = $client->query($query);

$response = $queryResponse->getResponse();

print_r($response);

?>
```

### See Also

-   <span class="methodname">SolrQuery::collapse</span>

SolrCollapseFunction::getField
==============================

Returns the field that is being collapsed on

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrCollapseFunction::getField</span> ( <span
class="methodparam">void</span> )

Returns the field that is being collapsed on.

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrCollapseFunction::setField</span>

SolrCollapseFunction::getHint
=============================

Returns collapse hint

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrCollapseFunction::getHint</span> ( <span
class="methodparam">void</span> )

Returns collapse hint

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrCollapseFunction::setHint</span>

SolrCollapseFunction::getMax
============================

Returns max parameter

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrCollapseFunction::getMax</span> ( <span
class="methodparam">void</span> )

Returns max parameter

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrCollapseFunction::setMax</span>

SolrCollapseFunction::getMin
============================

Returns min parameter

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrCollapseFunction::getMin</span> ( <span
class="methodparam">void</span> )

Returns min parameter

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrCollapseFunction::setMin</span>

SolrCollapseFunction::getNullPolicy
===================================

Returns null policy

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrCollapseFunction::getNullPolicy</span> (
<span class="methodparam">void</span> )

Returns null policy used or null

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrCollapseFunction::setNullPolicy</span>

SolrCollapseFunction::getSize
=============================

Returns size parameter

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SolrCollapseFunction::getSize</span> ( <span
class="methodparam">void</span> )

Gets the initial size of the collapse data structures when collapsing on
a numeric field only

### Parameters

This function has no parameters.

### Return Values

### See Also

-   <span class="methodname">SolrCollapseFunction::setSize</span>

SolrCollapseFunction::setField
==============================

Sets the field to collapse on

### Description

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">SolrCollapseFunction::setField</span> ( <span
class="methodparam"><span class="type">string</span> `$fieldName`</span>
)

The field name to collapse on. In order to collapse a result. The field
type must be a single valued String, Int or Float.

### Parameters

`fieldName`  

### Return Values

<span class="type">SolrCollapseFunction</span>

SolrCollapseFunction::setHint
=============================

Sets collapse hint

### Description

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">SolrCollapseFunction::setHint</span> ( <span
class="methodparam"><span class="type">string</span> `$hint`</span> )

Sets collapse hint

### Parameters

`hint`  
Currently there is only one hint available "top\_fc", which stands for
top level FieldCache

### Return Values

<span class="type">SolrCollapseFunction</span>

### Examples

**Example \#1 <span
class="function">SolrCollapseFunction::setHint</span> example**

``` php
<?php

/* ... */

?>
```

The above example will output something similar to:

    ...

SolrCollapseFunction::setMax
============================

Selects the group heads by the max value of a numeric field or function
query

### Description

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">SolrCollapseFunction::setMax</span> ( <span
class="methodparam"><span class="type">string</span> `$max`</span> )

Selects the group heads by the max value of a numeric field or function
query.

### Parameters

`max`  

### Return Values

<span class="type">SolrCollapseFunction</span>

### Examples

**Example \#1 <span class="function">SolrCollapseFunction::setMax</span>
example**

``` php
<?php

$func = new SolrCollapseFunction('field_name');

$func->setMax('sum(cscore(),field(some_field))');

$query = new SolrQuery('*:*');

$query->collapse($func);

?>
```

SolrCollapseFunction::setMin
============================

Sets the initial size of the collapse data structures when collapsing on
a numeric field only

### Description

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">SolrCollapseFunction::setMin</span> ( <span
class="methodparam"><span class="type">string</span> `$min`</span> )

Sets the initial size of the collapse data structures when collapsing on
a numeric field only

### Parameters

`min`  

### Return Values

<span class="type">SolrCollapseFunction</span>

SolrCollapseFunction::setNullPolicy
===================================

Sets the NULL Policy

### Description

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">SolrCollapseFunction::setNullPolicy</span> ( <span
class="methodparam"><span class="type">string</span>
`$nullPolicy`</span> )

Sets the NULL Policy. One of the 3 policies defined as class constants
shall be passed. Accepts ignore, expand, or collapse policies.

### Parameters

`nullPolicy`  

### Return Values

<span class="type">SolrCollapseFunction</span>

SolrCollapseFunction::setSize
=============================

Sets the initial size of the collapse data structures when collapsing on
a numeric field only

### Description

<span class="modifier">public</span> <span
class="type">SolrCollapseFunction</span> <span
class="methodname">SolrCollapseFunction::setSize</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> )

Sets the initial size of the collapse data structures when collapsing on
a numeric field only.

### Parameters

`size`  

### Return Values

<span class="type">SolrCollapseFunction</span>

SolrCollapseFunction::\_\_toString
==================================

Returns a string representing the constructed collapse function

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SolrCollapseFunction::\_\_toString</span> (
<span class="methodparam">void</span> )

Returns a string representing the constructed collapse function

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

This is the base class for all exception thrown by the Solr extension
classes.

Class synopsis
--------------

**SolrException**

<span class="ooclass"> class **SolrException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> <span class="type">int</span>
`$sourceline` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$sourcefile` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$zif_name` ;

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getInternalInfo</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`sourceline`  
The line in c-space source file where exception was generated

`sourcefile`  
The c-space source file where exception was generated

`zif_name`  
The c-space function where exception was generated

SolrException::getInternalInfo
==============================

Returns internal information where the Exception was thrown

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrException::getInternalInfo</span> ( <span
class="methodparam">void</span> )

Returns internal information where the Exception was thrown.

### Parameters

This function has no parameters.

### Return Values

Returns an array containing internal information where the error was
thrown. Used only for debugging by extension developers.

Introduction
------------

An exception thrown when there is an error while making a request to the
server from the client.

Class synopsis
--------------

**SolrClientException**

<span class="ooclass"> class **SolrClientException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **SolrException**
</span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$sourceline` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$sourcefile` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$zif_name` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getInternalInfo</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrException::getInternalInfo</span> ( <span
class="methodparam">void</span> )

}

SolrClientException::getInternalInfo
====================================

Returns internal information where the Exception was thrown

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrClientException::getInternalInfo</span> (
<span class="methodparam">void</span> )

Returns internal information where the Exception was thrown.

### Parameters

This function has no parameters.

### Return Values

Returns an array containing internal information where the error was
thrown. Used only for debugging by extension developers.

Introduction
------------

An exception thrown when there is an error produced by the Solr Server
itself.

Class synopsis
--------------

**SolrServerException**

<span class="ooclass"> class **SolrServerException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **SolrException**
</span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$sourceline` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$sourcefile` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$zif_name` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getInternalInfo</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrException::getInternalInfo</span> ( <span
class="methodparam">void</span> )

}

SolrServerException::getInternalInfo
====================================

Returns internal information where the Exception was thrown

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrServerException::getInternalInfo</span> (
<span class="methodparam">void</span> )

Returns internal information where the Exception was thrown.

### Parameters

This function has no parameters.

### Return Values

Returns an array containing internal information where the error was
thrown. Used only for debugging by extension developers.

Introduction
------------

This object is thrown when an illegal or invalid argument is passed to a
method.

Class synopsis
--------------

**SolrIllegalArgumentException**

<span class="ooclass"> class **SolrIllegalArgumentException** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**SolrException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$sourceline` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$sourcefile` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$zif_name` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getInternalInfo</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrException::getInternalInfo</span> ( <span
class="methodparam">void</span> )

}

SolrIllegalArgumentException::getInternalInfo
=============================================

Returns internal information where the Exception was thrown

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">SolrIllegalArgumentException::getInternalInfo</span>
( <span class="methodparam">void</span> )

Returns internal information where the Exception was thrown.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns an array containing internal information where the error was
thrown. Used only for debugging by extension developers.

Introduction
------------

This object is thrown when an illegal or unsupported operation is
performed on an object.

Class synopsis
--------------

**SolrIllegalOperationException**

<span class="ooclass"> class **SolrIllegalOperationException** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**SolrException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$sourceline` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$sourcefile` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$zif_name` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getInternalInfo</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrException::getInternalInfo</span> ( <span
class="methodparam">void</span> )

}

SolrIllegalOperationException::getInternalInfo
==============================================

Returns internal information where the Exception was thrown

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">SolrIllegalOperationException::getInternalInfo</span>
( <span class="methodparam">void</span> )

Returns internal information where the Exception was thrown.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns an array containing internal information where the error was
thrown. Used only for debugging by extension developers.

Introduction
------------

Class synopsis
--------------

**SolrMissingMandatoryParameterException**

<span class="ooclass"> class **SolrMissingMandatoryParameterException**
</span> <span class="ooclass"> <span class="modifier">extends</span>
**SolrException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$sourceline` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$sourcefile` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$zif_name` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SolrException::getInternalInfo</span> ( <span
class="methodparam">void</span> )

}
