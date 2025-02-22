# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.


# where to put generated libraries
set(LIBRARY_OUTPUT_PATH "${BUILD_OUTPUT_ROOT_DIRECTORY}/thrift")

# where to put generated binaries
set(EXECUTABLE_OUTPUT_PATH "${BUILD_OUTPUT_ROOT_DIRECTORY}/thrift")

set(SRC_FILES
  CatalogObjects_constants.cpp
  CatalogObjects_types.cpp
  CatalogService.cpp
  CatalogService_constants.cpp
  CatalogService_types.cpp
  CatalogInternalService_constants.cpp
  CatalogInternalService_types.cpp
  ImpalaInternalService_constants.cpp
  ImpalaInternalService_types.cpp
  ImpalaService.cpp
  ImpalaService_constants.cpp
  ImpalaService_types.cpp
  ImpalaHiveServer2Service.cpp
  beeswax_constants.cpp
  beeswax_types.cpp
  BackendGflags_constants.cpp
  BackendGflags_types.cpp
  BeeswaxService.cpp
  TCLIService.cpp
  TCLIService_constants.cpp
  TCLIService_types.cpp
  Data_constants.cpp
  Data_types.cpp
  DataSinks_constants.cpp
  DataSinks_types.cpp
  Descriptors_constants.cpp
  Descriptors_types.cpp
  ErrorCodes_types.cpp
  ErrorCodes_constants.cpp
  ExecStats_constants.cpp
  ExecStats_types.cpp
  Exprs_constants.cpp
  Exprs_types.cpp
  ExternalDataSource_constants.cpp
  ExternalDataSource_types.cpp
  Frontend_types.cpp
  Frontend_constants.cpp
  hive_metastore_constants.cpp
  hive_metastore_types.cpp
  JniCatalog_constants.cpp
  JniCatalog_types.cpp
  Logging_types.cpp
  LineageGraph_types.cpp
  LineageGraph_constants.cpp
  Metrics_constants.cpp
  Metrics_types.cpp
  MetricDefs_constants.cpp
  MetricDefs_types.cpp
  NetworkTest_constants.cpp
  NetworkTest_types.cpp
  NetworkTestService.cpp
  PlanNodes_constants.cpp
  PlanNodes_types.cpp
  Results_constants.cpp
  Results_types.cpp
  Partitions_constants.cpp
  Partitions_types.cpp
  Planner_constants.cpp
  Planner_types.cpp
  parquet_constants.cpp
  parquet_types.cpp
  Query_constants.cpp
  Query_types.cpp
  ResourceProfile_constants.cpp
  ResourceProfile_types.cpp
  RuntimeProfile_constants.cpp
  RuntimeProfile_types.cpp
  SqlConstraints_constants.cpp
  SqlConstraints_types.cpp
  StatestoreService.cpp
  StatestoreService_constants.cpp
  StatestoreService_types.cpp
  StatestoreSubscriber.cpp
  Status_constants.cpp
  Status_types.cpp
  Types_constants.cpp
  Types_types.cpp
  Zip_constants.cpp
  Zip_types.cpp
)

# keep everything in one library, the object files reference
# each other
add_library(ImpalaThrift ${SRC_FILES})

# Setting these files as code-generated lets make clean and incremental builds work
# correctly
set_source_files_properties(${SRC_FILES} PROPERTIES GENERATED TRUE)

add_dependencies(ImpalaThrift thrift-deps)
